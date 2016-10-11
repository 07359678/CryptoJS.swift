# CryptoJS.swift
Cross device cryptography in swift using the [Crypto JS library](https://code.google.com/p/crypto-js/) (Thanks to Jeff Mott).

Allows you to share the same crypto between a native iOS/OSX application and a web application.

##### Installation

Drag and drop CryptoJS.swift and the .js files in your Xcode project.

#### AES encryption

```swift
// Basic encryption
let AES = CryptoJS.AES()
let encrypted = AES.encrypt("secretMessage", secretKey: "password123")

// Custom IV
let encrypted = AES.encrypt("secretMessage", secretKey: "password123", options:["iv":123])

// Custom mode and padding
CryptoJS.mode.ECB() // Load custom mode
CryptoJS.pad.Iso97971() // Load custom padding scheme
let encrypted = AES.encrypt("secretMessage", secretKey: "password123", options:[ "mode": CryptoJS.mode().ECB, "padding": CryptoJS.pad().Iso97971 ])

// Supported modes: CBC (the default), CFB, CTR, OFB, ECB
// Supported padding schemes: Pkcs7 (the default), Iso97971, AnsiX923, Iso10126, ZeroPadding, NoPadding
```

#### AES decryption

```swift
// Basic decryption
let AES = CryptoJS.AES()
let decrypted = AES.decrypt(encrypted, secretKey: "password123")

// Custom mode and padding
CryptoJS.mode.ECB() // Load custom mode
CryptoJS.pad.Iso97971() // Load custom padding scheme
let decrypted = AES.decrypt(encrypted, secretKey: "password123", options:[ "mode": CryptoJS.mode().ECB, "padding": CryptoJS.pad().Iso97971 ])
```

#### TripleDES encryption

```swift
let TripleDES = CryptoJS.TripleDES()
let encrypted = TripleDES.encrypt("secretMessage", secretKey: "password123")
```

#### TripleDES decryption

```swift
let decrypted = TripleDES.decrypt(encrypted, secretKey: "password123")
```

#### Hashers

```swift
let MD5 = CryptoJS.MD5()
let SHA1 = CryptoJS.SHA1()
let SHA224 = CryptoJS.SHA224()
let SHA256 = CryptoJS.SHA256()
let SHA384 = CryptoJS.SHA384()
let SHA512 = CryptoJS.SHA512()
let SHA3 = CryptoJS.SHA3()
let RIPEMD160 = CryptoJS.RIPEMD160()

var hash = MD5.hash("mystring")
var hash = SHA1.hash("mystring")
var hash = SHA224.hash("mystring")
var hash = SHA256.hash("mystring")
var hash = SHA384.hash("mystring")
var hash = SHA3.hash("mystring")
var hash = SHA512.hash("mystring")
var hash = SHA3.hash("mystring",outputLength: 256)
var hash = RIPEMD160.hash("mystring")
```

######Feel free to contribute!
