## Component Information

| Field Name               | Value                            |
|:-------------------------|:---------------------------------|
| **Name**                 | ${{ values.name }}               |
| **Fully Qualified Name** | ${{ values.fullyQualifiedName }} |
| **Description**          | ${{ values.description }}        |
| **Domain**               | ${{ values.domain }}             |
| **Data Product**         | ${{ values.dataproduct }}        |
| **Identifier**           | ${{ values.identifier }}         |

{% if values.schemaColumns | length > 0 %}
## Data contract schema

| Column | Data type | Description |
|:-------|:----------|:------------|
{%- for column in values.schemaColumns %}
| ${{ column.name }} | ${{ column.dataType }} | ${{ column.description if column.description else "-" }} |
{%- endfor %}

For other details about each column, please refer to this component `catalog-info.yaml`
{%- endif %}

## HDFS Information

| Field Name           | Value                   |
|:---------------------|:------------------------|
| **HDFS Storage URN** | ${{ values.dependsOn }} |
