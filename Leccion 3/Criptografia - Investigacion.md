


# Los formatos de claves más comunes son

|Formato|Extensión típica|Usado por / compatibilidad|Comentario|
|---|---|---|---|
|**PPK**|`.ppk`|PuTTY, WinSCP|Formato propietario de PuTTY; no se puede usar directamente en OpenSSH.|
|**PEM**|`.pem`|OpenSSH, OpenSSL, servidores web|Base64 con encabezados `-----BEGIN PRIVATE KEY-----`; muy usado en TLS/SSL y SSH.|
|**OpenSSH**|`id_rsa`, `id_ed25519` (sin extensión o `.pub` para pública)|OpenSSH, Linux/macOS, Windows OpenSSH|Formato nativo de OpenSSH. Claves privadas y públicas separadas.|
|**PKCS#8**|`.key`, `.pem`|OpenSSL, Java, algunos servicios|Puede contener claves privadas en estándar interoperable; admite cifrado.|
|**PKCS#12 / PFX**|`.p12`, `.pfx`|Windows, OpenSSL|Contiene certificado + clave privada + cadena completa, usado para TLS/SSL.|
|**CER / CRT**|`.cer`, `.crt`|Windows, Linux|Certificados públicos; no contienen la clave privada.|
|**DER**|`.der`|Java, OpenSSL|Formato binario de certificado; alternativa a PEM.|
