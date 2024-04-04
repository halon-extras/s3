# S3 Object Storage 
An S3 object storage implementation written in HSL

## Installation

Follow the [instructions](https://docs.halon.io/manual/comp_install.html#installation) in our manual to add our package repository and then run the below command.

### Ubuntu

```
apt-get install halon-extras-s3
```

### RHEL

```
yum install halon-extras-s3
```

## Exported functions

These functions needs to be [imported](https://docs.halon.io/hsl/structures.html#import) from the `extras://s3` module path.

### s3_put($endpoint, $secretkey, $accesskey, $bucket, $name, $fp, $options = [])

**Params**

- endpoint `string` - the endpoint (including https://)
- secretkey `string` - the secretkey
- accesskey `string` - the accesskey
- bucket `string` - the bucket
- name `string` - the name
- fp `File` - the mail file
- options `array` - an options array
   - http-background `array` - http-background options
     - id `string` - the http-background id

**Returns**

The ``s3_put`` functions returns the result of the [``http_background``](https://github.com/halon-extras/http-background/) call.

**Example (EOD)**

```
import { s3_put } from "extras://s3";

echo s3_put(
            $endpoint,
            $secretkey,
            $accesskey,
            $bucket,
            "hello.txt",
            File::String("Hello World")
        );
```

### s3_get($endpoint, $secretkey, $accesskey, $bucket, $name, $options = [])

**Params**

- endpoint `string` - the endpoint (including https://)
- secretkey `string` - the secretkey
- accesskey `string` - the accesskey
- bucket `string` - the bucket
- name `string` - the name
- options `array` - an options array
   - http-background `array` - http-background options
     - id `string` - the http-background id

**Returns**

The ``s3_get`` functions returns the result of the [``http_background``](https://github.com/halon-extras/http-background/) call.

**Example (EOD)**

```
import { s3_get } from "extras://s3";

echo s3_get(
            $endpoint,
            $secretkey,
            $accesskey,
            $bucket,
            "hello.txt"
        );
```

### s3_delete($endpoint, $secretkey, $accesskey, $bucket, $name, $options = [])

**Params**

- endpoint `string` - the endpoint (including https://)
- secretkey `string` - the secretkey
- accesskey `string` - the accesskey
- bucket `string` - the bucket
- name `string` - the name
- options `array` - an options array
   - http-background `array` - http-background options
     - id `string` - the http-background id

**Returns**

The ``s3_delete`` functions returns the result of the [``http_background``](https://github.com/halon-extras/http-background/) call.

**Example (EOD)**

```
import { s3_delete } from "extras://s3";

echo s3_delete(
            $endpoint,
            $secretkey,
            $accesskey,
            $bucket,
            "hello.txt"
        );
```