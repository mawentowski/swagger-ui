Certainly, here are examples of how you can define schemas for each of these data types, specifying their attributes as metadata:


```yaml
components:
  schemas:
    Email:
      type: string
      description: A string value with specific format and constraints.
      format: email
      maxLength: 100
      pattern: "^\\w+@\\w+\\.\\w+$"
```


```yaml
components:
  schemas:
    BooleanDefinition:
      type: boolean
      description: A boolean value representing true or false.
      example: true

```

```yaml
components:
  schemas:
    NumberDefinition:
      type: number
      description: A numeric value with specified range, precision, and units.
      minimum: 0
      maximum: 100
      multipleOf: 5
      unit: meters

```

```yaml
components:
  schemas:
    NumberDefinition:
      type: number
      description: A numeric value with specified range, precision, and units.
      minimum: 0
      maximum: 100
      multipleOf: 5
      unit: meters

```



```yaml
components:
  schemas:
    ArrayDefinition:
      type: array
      description: An array with specific allowed values, size limits, and ordering.
      minItems: 1
      maxItems: 10
      uniqueItems: true
      items:
        type: string
        enum: ["value1", "value2", "value3"]

```


```yaml
components:
  schemas:
    DateTimeDefinition:
      type: string
      description: A date and time with a specified format, time zone, and special considerations.
      format: date-time
      example: "2023-10-26T14:30:00-05:00"
```



```yaml
components:
  schemas:
    StatusEnum:
      type: string
      description: An enumeration of possible status values.
      enum: ["active", "inactive", "deleted"]
```

How to reference: 
```yaml
paths:
  /example:
    post:
      parameters:
        - name: yourParameterName
          in: query  # Use the appropriate 'in' value, e.g., query, path, header, etc.
          schema:
            $ref: '#/components/schemas/StringDefinition'
          description: A description of your parameter
```

## Notes

Additionally, consider enhancing reusability by creating dedicated components to define and manage metadata.

        To achieve consistency, follow the [centralize field definitions in components](#central-definition) rule.



status
enum
The status of the payment is either succeeded, pending, or failed.



```yaml

```
