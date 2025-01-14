<h1>LightDB</h1>


<h2>What is this?</h2>

LightDB is a lightweight JSON Database for Python
that allows you to <b>quickly</b> and <b>easily</b> write data to a file


<h2>Installing</h2>

<pre lang="bash">
pip install git+https://github.com/9bany/LightDB.git
</pre>


<h2>How to use</h2>

<pre lang="python">
from lightdb import LightDB

db = LightDB("/path/to/file.json") # or a non-existent file, it will be created automatically

# SET method:

data = {
    "key1": "value1",
    "key2": [
        "value2",
        "value3",
        ...
    ],
    ...
}
db.set("key3", data)
data = ["value4", "value5"]
db.set("key4", data)


# or GET:

print(db.get("key3"))
# {"key1": "value1", "key2": ["value2", "value3"]}
print(db.get("key4"))
# ["value4", "value5"]

# or POP:

db.pop("key") # return popped key

# SET KEY method:

data = {
    "key5": "value1",
    "key6": "value2"
}
db.set_key("name", "key7", data)
data = ["key8", "key9"]
db.set_key("name", "key10", data)


# or GET KEY:

print(db.get_key("name", "key7"))
# {"key5": "value1", "key6": "value2"}
print(db.get_key("name", "key10"))
# ["key8", "key9"]


# or POP KEY:

db.pop_key("name", "key") # return popped key
</pre>
