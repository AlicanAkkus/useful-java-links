## Json Hello World examples

The Json parsers libraries offers 3 main methods for processing JSON and 1 additional:
1. **Data Binding** converts JSON to and from POJOs based either on property accessor conventions or annotations.
2. **Tree Model** provides a mutable in-memory tree representation of a JSON document.
3. **Streaming API** (aka "Incremental parsing/generation") reads and writes JSON content as discrete events.
4 (additional) **Analog XPath** - working with a JSON structure in the same way as XPath expression are used in combination with an XML document.

### 1. Json parsers overview 

**Property** | [Fastjson ](https://github.com/alibaba/fastjson)| [Gson](https://github.com/google/gson) |  [LoganSquare](https://github.com/bluelinelabs/LoganSquare) | [JSON java](https://github.com/stleary/JSON-java) |  [Moshi](https://github.com/square/moshi) | [Ig json parser](https://github.com/Instagram/ig-json-parser) | [Jackson](http://wiki.fasterxml.com/JacksonHome) | [Genson](http://owlike.github.io/genson/) | [JsonPath](https://github.com/jayway/JsonPath) 
 ----------	 | --- | --- |  --- | --- |  --- | --- | --- | --- | --- 
1. Data bind | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/fastjson)| [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/gson) | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/logansquare)  | - | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/moshi) | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/ig_json_parser) | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/jackson) | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/genson) | - 
2. Tree Model | - | [Yes](https://github.com/Vedenin/useful-java-links/blob/master/helloworlds/3.8-json/gson/src/main/java/gson/advanced/TreeModel.java)| -  | - | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/json_java) | - | [Yes](https://github.com/Vedenin/useful-java-links/blob/master/helloworlds/3.8-json/jackson/src/main/java/jackson/advanced/TreeModel.java) | - | - 
3. Streaming API | - | [Yes](https://github.com/Vedenin/useful-java-links/blob/master/helloworlds/3.8-json/gson/src/main/java/gson/advanced/StreamingAPI.java)| -  | - | - | - | [Yes](https://github.com/Vedenin/useful-java-links/blob/master/helloworlds/3.8-json/jackson/src/main/java/jackson/advanced/StreamingAPI.java) | - | - 
4. Analog XPath | [Yes](https://github.com/Vedenin/useful-java-links/blob/master/helloworlds/3.8-json/fastjson/src/main/java/fastjson/JsonPathHelloWorld.java) | - | -  | - | - | - | - | - | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/json_path)
5. Generation classes at compile-time | - | - | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/logansquare)  | - | - | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/ig_json_parser) | - | - | -
6. Github's star | 4851 | 4120 | 2188  | 1937 | 1732 | 921 | 881 | 108 | 849
7. Working with static inner class | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/fastjson) | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/gson) | [No](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/logansquare) | - | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/moshi) | [No](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/ig_json_parser) | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/jackson) | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/genson) | -
8. Required annotations | [No](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/fastjson) | [No](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/gson)  | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/logansquare) | - | [No](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/moshi)  | [Yes](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/ig_json_parser) | [No](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/jackson)  | [No](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/genson)  | -

### 2. Json parsers using Data bind

Methods	 | [Fastjson ](https://github.com/alibaba/fastjson)| [Gson](https://github.com/google/gson) |  [LoganSquare](https://github.com/bluelinelabs/LoganSquare) | [Moshi](https://github.com/square/moshi) | [Ig json parser](https://github.com/Instagram/ig-json-parser) | [Jackson](http://wiki.fasterxml.com/JacksonHome) | [Genson](http://owlike.github.io/genson/) 
 ----------	 | --- | --- |  --- | --- |  --- | --- | --- 
Initialization | --- | `Gson gson = new Gson()` |  --- |`Moshi moshi = new Moshi.`<br>`Builder().build(); JsonAdapter<Human>`<br>`jsonAdapter = moshi.adapter(Human.class)`|  --- | `ObjectMapper mapper = new ObjectMapper()` | `Genson genson = new Genson()` 
From Java to Json | `JSON.toJSONString(human)` | `gson.toJson(human)` |  `LoganSquare.serialize(human)` | `jsonAdapter.toJson(human)` |  `Human__JsonHelper.serializeToJson(human)` | `mapper.writeValueAsString(human)` | `genson.serialize(human)` 
From Json to Java | `JSON.parseObject(jsonString, Human.class)` | `gson.fromJson(jsonString, Human.class)` |  `LoganSquare.parse(jsonString, Human.class)` | `jsonAdapter.fromJson(jsonString)` |  `Human__JsonHelper.parseFromJson(jsonString)` | `mapper.readValue(jsonString, Human.class)` | `genson.deserialize(jsonString, Human.class)`

**Json and Java classes for every examples**:

**json**:
```javascript
jsonString =
{
  "message": "Hi",
  "place": {
    "name": "World"
  }
}
```

**Java classes** 
```java
    class Human {
        private String message;
        private Place place;

        public String getMessage() {
            return message;
        }

        public void setMessage(String message) {
            this.message = message;
        }

        public Place getPlace() {
            return place;
        }

        public void setPlace(Place place) {
            this.place = place;
        }

        public void say() {
            System.out.println();
            System.out.println(getMessage() + " , " + getPlace().getName() + "!");
        }
    }

    class Place {
        private String name;

        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }
    }
```
        // init class
        Place place = new Place();
        place.setName("World");

        Human human = new Human();
        human.setMessage("Hi");
        human.setPlace(place);

**Examples**:

**1) Fastjson**:
```java
        // convert to json
        String jsonString = JSON.toJSONString(human);
        System.out.println("json " + jsonString); //  print "json {"message":"Hi","place":{"name":"World"}}"

        // convert from json
        Human newHuman = JSON.parseObject(jsonString, Human.class);
        newHuman.say(); //  print "Hi , World!"
```
[Full example](https://github.com/Vedenin/useful-java-links/blob/master/helloworlds/3.8-json/fastjson/src/main/java/fastjson/FastJsonHelloWorld.java)

**2) Gson**
```java
        // convert to json
        Gson gson = new Gson();
        String jsonString = gson.toJson(human);
        System.out.println("json " + jsonString); //  print   "json {"message":"Hi","place":{"name":"World"}}"

        // convert from json
        Human newHuman = gson.fromJson(jsonString, Human.class);
        newHuman.say(); //  print   "Hi , World!"

```
[Full example](https://github.com/Vedenin/useful-java-links/blob/master/helloworlds/3.8-json/gson/src/main/java/gson/GsonHelloWorld.java)

**3) LoganSquare**
```java
@JsonObject
public class Human {
    @JsonField(name="message")
    public String message;
    @JsonField(name="place")
    public Place place;

       ....

        // convert to json
        String jsonString = LoganSquare.serialize(human);
        System.out.println("json " + jsonString); // print  "json {"place":{"name":"World"},"message":"Hi"}"

        // convert from json
        Human newHuman = LoganSquare.parse(jsonString, Human.class);
        newHuman.say(); // print  "Hi , World!"

```
[Full example](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/logansquare/src/main/java/logansquare)

**4) Moshi**
```java
        // convert to json
        Moshi moshi = new Moshi.Builder().build();
        JsonAdapter<Human> jsonAdapter = moshi.adapter(Human.class);

        String jsonString = jsonAdapter.toJson(human);
        System.out.println("json " + jsonString); // print   "json {"message":"Hi","place":{"name":"World"}}"

        // convert from json
        Human newHuman = jsonAdapter.fromJson(jsonString);
        newHuman.say(); //  print  "Hi , World!"

```
[Full example](https://github.com/Vedenin/useful-java-links/blob/master/helloworlds/3.8-json/moshi/src/main/java/moshi/MoshiHelloWorld.java)

**5) Ig json parser**
```java
@JsonType
public class Human {
    @JsonField(fieldName="message")
    public String message;
    @JsonField(fieldName="place")
    public Place place;

        ...

        // convert to json
        String jsonString = Human__JsonHelper.serializeToJson(human);
        System.out.println("json " + jsonString); // print   "json {"place":{"name":"World"},"message":"Hi"}"

        // convert from json
        Human newHuman = Human__JsonHelper.parseFromJson(jsonString);
        newHuman.say(); //  print  "Hi , World!"
```
[Full example](https://github.com/Vedenin/useful-java-links/tree/master/helloworlds/3.8-json/ig_json_parser/src/main/java/ig_json_parser)

**5. Jackson**
```java
        // convert to json
        ObjectMapper mapper = new ObjectMapper();
        String jsonString = mapper.writeValueAsString(human);
        System.out.println("json " + jsonString); //  print   "json {"message":"Hi","place":{"name":"World"}}"

        // convert from json
        Human newHuman = mapper.readValue(jsonString, Human.class);
        newHuman.say(); //  print  "Hi , World!"
```
[Full example](https://github.com/Vedenin/useful-java-links/blob/master/helloworlds/3.8-json/jackson/src/main/java/jackson/JacksonHelloWorld.java)

**6. Genson**
```java
        // convert to json
        String jsonString = new Genson().serialize(human);

        System.out.println("json " + jsonString); // print   "json {"message":"Hi","place":{"name":"World"}}"

        // convert from json
        Human newHuman =  new Genson().deserialize(jsonString, Human.class);
        newHuman.say(); //  print   "Hi , World!"
```
[Full example](https://github.com/Vedenin/useful-java-links/blob/master/helloworlds/3.8-json/genson/src/main/java/genson/GensonHelloWorld.java)

### 3. Json parsers using Tree Model

From Json to Java:

Methods	 | [Gson](https://github.com/google/gson) | [Jackson](http://wiki.fasterxml.com/JacksonHome) | [JSON java](https://github.com/stleary/JSON-java)
---------- 	 | --- | --- |  --- 
Initialization| `JsonParser parser = new JsonParser()` |  `new ObjectMapper()` |  - 
Json parsing	 |  `parser.parse(<string>)` | `mapper.readValue(<string>, JsonNode.class)` |  `new JSONObject(<string>)` 
Get main object | `root.getAsJsonObject()` | - |  - 
Get string value | `root.get(<name>).getAsString()` | `root.get(<name>).asText()` |  `root.getString(<name>)` 
Get child object | `root.getAsJsonObject(<name>)` | `root.get(<name>)` |  `root.getJSONObject(<name>)` 

From Java to Json:

Methods	 | [Gson](https://github.com/google/gson) | [Jackson](http://wiki.fasterxml.com/JacksonHome) | [JSON java](https://github.com/stleary/JSON-java)
---------- 	 | --- | --- |  --- 
Initialization| -  |  `new ObjectMapper()` |  - 
Create main object| `new JsonObject()` |  `mapper.createObjectNode()` |  `new JSONObject()`
Add string field | `root.addProperty(<name>, <string>)` | `root.put(<name>, <string>)` |  `root.put(<name>, <string>)` 
Add child object | `root.add(<name>, <object>);` | `root.putObject(<name>)` |   `root.put(<name>, <object>)` 

