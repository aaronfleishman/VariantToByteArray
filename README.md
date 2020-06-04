# VariantToByteArray
Flexible VI for LabVIEW that will convert most datatypes into a byte array without adding anything extra, such as array size or data type codes.

Developed using LabVIEW 2020 Community Edition.

Detailed Description

This VI will convert a variant to a byte array without adding anything extra other than the data itself. This works well as a general function for converting a variant of simple or hierarchal (cluster) numeric data into a byte array. You only need to convert the data to Variant prior to processing it with this function. Also, this specifically avoids the use of property nodes so that the function can be used on RT targets with no worries of it not working due to property node limitations with front panels on RT targets.

This differs from a method like Flatten To String + String to Byte Array. That method prepends array sizes into the byte array on any array within a cluster, even with Prepend Array or String Size set to False, as this only applies to the highest level of the datatype being input. Furthermore, it is more applicable than Type Cast on a cluster because it works on complicated cluster types that include arrays and subclusters.

A list of supported datatypes is below.

Datatypes currently supported
- I8
- I16
- I32
- I64
- U8
- U16
- U32
- U64
- Single Float
- Double Float
- Extended Float
- Enum U8
- Enum U16
- Enum U32
- Enum U64
- Boolean (converts to single byte)
- String
- Path (converts to string, and then to byte array)
- Array (only works with elements of types above)
- Cluster (recursive. only works with clusters of types above, or arrays with types above)
- Cluster of Arrays (supported, recursive)

Not Supported (yet)
- Array of Clusters
