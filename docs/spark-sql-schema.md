# Schema &mdash; Structure of Data

A **schema** is the description of the structure of your data (which together create a [Dataset](Dataset.md) in Spark SQL). It can be *implicit* (and <<implicit-schema, inferred at runtime>>) or *explicit* (and known at compile time).

A schema is described using [StructType](StructType.md) which is a collection of spark-sql-StructField.md[StructField] objects (that in turn are tuples of names, types, and `nullability` classifier).

`StructType` and `StructField` belong to the `org.apache.spark.sql.types` package.

[source, scala]
----
import org.apache.spark.sql.types.StructType
val schemaUntyped = new StructType()
  .add("a", "int")
  .add("b", "string")

// alternatively using Schema DSL
val schemaUntyped_2 = new StructType()
  .add($"a".int)
  .add($"b".string)
----

You can use the canonical string representation of SQL types to describe the types in a schema (that is inherently untyped at compile type) or use type-safe types from the `org.apache.spark.sql.types` package.

[source, scala]
----
// it is equivalent to the above expressions
import org.apache.spark.sql.types.{IntegerType, StringType}
val schemaTyped = new StructType()
  .add("a", IntegerType)
  .add("b", StringType)
----

TIP: Read up on spark-sql-CatalystSqlParser.md[CatalystSqlParser] that is responsible for parsing data types.

It is however recommended to use the singleton [DataTypes](DataType.md#DataTypes) class with static methods to create schema types.

```text
import org.apache.spark.sql.types.DataTypes._
val schemaWithMap = StructType(
  StructField("map", createMapType(LongType, StringType), false) :: Nil)
```

[StructType](StructType.md) offers [printTreeString](#printTreeString) that makes presenting the schema more user-friendly.

```text
scala> schemaTyped.printTreeString
root
 |-- a: integer (nullable = true)
 |-- b: string (nullable = true)

scala> schemaWithMap.printTreeString
root
|-- map: map (nullable = false)
|    |-- key: long
|    |-- value: string (valueContainsNull = true)

// You can use prettyJson method on any DataType
scala> println(schema1.prettyJson)
{
 "type" : "struct",
 "fields" : [ {
   "name" : "a",
   "type" : "integer",
   "nullable" : true,
   "metadata" : { }
 }, {
   "name" : "b",
   "type" : "string",
   "nullable" : true,
   "metadata" : { }
 } ]
}
```

As of Spark 2.0, you can describe the schema of your strongly-typed datasets using spark-sql-Encoder.md[encoders].

[source, scala]
----
import org.apache.spark.sql.Encoders

scala> Encoders.INT.schema.printTreeString
root
 |-- value: integer (nullable = true)

scala> Encoders.product[(String, java.sql.Timestamp)].schema.printTreeString
root
|-- _1: string (nullable = true)
|-- _2: timestamp (nullable = true)

case class Person(id: Long, name: String)
scala> Encoders.product[Person].schema.printTreeString
root
 |-- id: long (nullable = false)
 |-- name: string (nullable = true)
----

=== [[implicit-schema]] Implicit Schema

[source, scala]
----
val df = Seq((0, s"""hello\tworld"""), (1, "two  spaces inside")).toDF("label", "sentence")

scala> df.printSchema
root
 |-- label: integer (nullable = false)
 |-- sentence: string (nullable = true)

scala> df.schema
res0: org.apache.spark.sql.types.StructType = StructType(StructField(label,IntegerType,false), StructField(sentence,StringType,true))

scala> df.schema("label").dataType
res1: org.apache.spark.sql.types.DataType = IntegerType
----
