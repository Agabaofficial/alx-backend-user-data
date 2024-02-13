Background Context
In this project, you will learn what the authentication process means and implement a Basic Authentication on a simple API.

In the industry, you should not implement your own Basic authentication system and use a module or framework that doing it for you (like in Python-Flask: Flask-HTTPAuth). Here, for the learning purpose, we will walk through each step of this mechanism to understand it by doing.

This module provides functions for encoding binary data to printable ASCII characters and decoding such encodings back to binary data. It provides encoding and decoding functions for the encodings specified in RFC 3548, which defines the Base16, Base32, and Base64 algorithms, and for the de-facto standard Ascii85 and Base85 encodings.

The RFC 3548 encodings are suitable for encoding binary data so that it can safely sent by email, used as parts of URLs, or included as part of an HTTP POST request. The encoding algorithm is not the same as the uuencode program.

There are two interfaces provided by this module. The modern interface supports encoding bytes-like objects to ASCII bytes, and decoding bytes-like objects or strings containing ASCII to bytes. Both base-64 alphabets defined in RFC 3548 (normal, and URL- and filesystem-safe) are supported.

The legacy interface does not support decoding from strings, but it does provide functions for encoding and decoding to and from file objects. It only supports the Base64 standard alphabet, and it adds newlines every 76 characters as per RFC 2045. Note that if you are looking for RFC 2045 support you probably want to be looking at the email package instead.

Changed in version 3.3: ASCII-only Unicode strings are now accepted by the decoding functions of the modern interface.

Changed in version 3.4: Any bytes-like objects are now accepted by all encoding and decoding functions in this module. Ascii85/Base85 support added.

The modern interface provides:

base64.b64encode(s, altchars=None)
Encode the bytes-like object s using Base64 and return the encoded bytes.

Optional altchars must be a bytes-like object of at least length 2 (additional characters are ignored) which specifies an alternative alphabet for the + and / characters. This allows an application to e.g. generate URL or filesystem safe Base64 strings. The default is None, for which the standard Base64 alphabet is used.

base64.b64decode(s, altchars=None, validate=False)
Decode the Base64 encoded bytes-like object or ASCII string s and return the decoded bytes.

Optional altchars must be a bytes-like object or ASCII string of at least length 2 (additional characters are ignored) which specifies the alternative alphabet used instead of the + and / characters.

A binascii.Error exception is raised if s is incorrectly padded.

If validate is False (the default), characters that are neither in the normal base-64 alphabet nor the alternative alphabet are discarded prior to the padding check. If validate is True, these non-alphabet characters in the input result in a binascii.Error.

base64.standard_b64encode(s)
Encode bytes-like object s using the standard Base64 alphabet and return the encoded bytes.

base64.standard_b64decode(s)
Decode bytes-like object or ASCII string s using the standard Base64 alphabet and return the decoded bytes.

base64.urlsafe_b64encode(s)
Encode bytes-like object s using the URL- and filesystem-safe alphabet, which substitutes - instead of + and _ instead of / in the standard Base64 alphabet, and return the encoded bytes. The result can still contain =.

base64.urlsafe_b64decode(s)
Decode bytes-like object or ASCII string s using the URL- and filesystem-safe alphabet, which substitutes - instead of + and _ instead of / in the standard Base64 alphabet, and return the decoded bytes.

base64.b32encode(s)
Encode the bytes-like object s using Base32 and return the encoded bytes.

base64.b32decode(s, casefold=False, map01=None)
Decode the Base32 encoded bytes-like object or ASCII string s and return the decoded bytes.

Optional casefold is a flag specifying whether a lowercase alphabet is acceptable as input. For security purposes, the default is False.

RFC 3548 allows for optional mapping of the digit 0 (zero) to the letter O (oh), and for optional mapping of the digit 1 (one) to either the letter I (eye) or letter L (el). The optional argument map01 when not None, specifies which letter the digit 1 should be mapped to (when map01 is not None, the digit 0 is always mapped to the letter O). For security purposes the default is None, so that 0 and 1 are not allowed in the input.

A binascii.Error is raised if s is incorrectly padded or if there are non-alphabet characters present in the input.

base64.b16encode(s)
Encode the bytes-like object s using Base16 and return the encoded bytes.

base64.b16decode(s, casefold=False)
Decode the Base16 encoded bytes-like object or ASCII string s and return the decoded bytes.

Optional casefold is a flag specifying whether a lowercase alphabet is acceptable as input. For security purposes, the default is False.

A binascii.Error is raised if s is incorrectly padded or if there are non-alphabet characters present in the input.