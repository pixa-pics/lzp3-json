# lzp3-json

Compress anything you can sum in a JSON into a Blob!  Now with LZP3 and web worker for multithreading.
Thanks God, lzp3 is blazing fast, impressive brains behind its conception.

```
import {LZP3} from "lzp3-json";

let pool = null;
//import workerpool from "workerpool";
//let pool = workerpool.pool(null, {minWorkers: "max"});

blob.arrayBuffer().then((array_buffer) => {

    const uint8a = new Uint8Array(array_buffer);
    LZP3(uint8a, "DECOMPRESS_UINT8A", (obj) => {

        // Get your javascript object back
    }, pool);
}, pool);

LZP3(obj, "COMPRESS_OBJECT", (uint8a) => {

    const blob = new Blob([uint8a], {type : "application/octet-stream"});
    // Store a blob in a DB from your javascript object
}, pool);
```
