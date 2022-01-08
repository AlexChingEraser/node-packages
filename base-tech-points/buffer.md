# Buffer

## Definition
represent a **fixed-length** sequence of **bytes**

## How to Use
subclass of `Uint8Array`, value: 0 ~ 255
use for character encodings or share memory

```javascript
import { Buffer } from 'buffer'
const buf = Buffer.from('tést', 'utf8'); //string 'tést'

const uint16array = new Uint16Array(buf.buffer, buf.byteOffet, buf.length / Uint16Array.BYTES_PER_ELEMENT)
// Uint16Array(5) [ 104, 101, 108, 108, 111 ]
```