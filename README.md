## Protocol Buffer

---

> How is Protocol Buffer used?

`Create a .protol file` -> `Automatically generate the code for any language`-> `serialization the data(deconde&encode)` -> `Send via network`

----

### .Protocol buffer definition

```protobuf
//Protocol buffer format
//syntax = "version of protocol buffer";
syntax = "protol3"; //using protocol buffer version 3

message NameOfMessage {
	//type name = field tag
	int numberID = 1;
	string name = 2;
	bool adult = 3;
}
```

> type: Int,float,double,bool,string,bytes
>
> type : repeat -> the array or a list

---

### Tag(importance part in Protocol buffer)

> small : 1 
>
> large : 2^29 
>
> Tag Not Be Able to use 1900 & 19999

**FOR THE TAG NUMBER**

* Tag 1 - 15 ： USING 1 BYTES => FOR frequently popular data
* Tag 2 - 2047 : USING 2 BYTES

---

### Default value the type

* Bool : false
* number : 0
* string : empty
* bytes : empty
* enum : the first value
* repeated : empty list

----

### Special Enum type

```protobuf
enum Name{
	TYPE_A = 0;
	TYPE_B = 1;
	TYPE_C = 2;
	TYPE_D = 3;
}

//message fiels
Name myEnum = 1;
```

---

> To Generate Code Need **Proto compiler : Protoc**

`command - protoc -I=“path of proto” --cpp/js/java/..._out=code "path/x.proto"`

