# Despedi3 🎉

##### Juanchi,
###### Ésta es mi cartita para vos. Un lindo problemita, que vas a tener que resolver para encontrar la siguiente pista.  :shipit:

######Espero esto te suene de algo, sino, buena suerte y hasta luego.

```java
import javax.crypto.spec.SecretKeySpec;
import javax.xml.bind.DatatypeConverter;
import java.security.Key;
import io.jsonwebtoken.*;
import java.util.Date;    
 
private String createJWT(String id, String issuer, String subject, long ttlMillis) {
 
    SignatureAlgorithm signatureAlgorithm = SignatureAlgorithm.HS256;
 
    long nowMillis = System.currentTimeMillis();
    Date now = new Date(nowMillis);
 
    byte[] apiKeySecretBytes = DatatypeConverter.parseBase64Binary(apiKey.getSecret());
    Key signingKey = new SecretKeySpec(apiKeySecretBytes, signatureAlgorithm.getJcaName());
 
    JwtBuilder builder = Jwts.builder().setId(id)
                                .setIssuedAt(now)
                                .setSubject(subject)
                                .setIssuer(issuer)
                                .signWith(signatureAlgorithm, signingKey);
 
    if (ttlMillis >= 0) {
    long expMillis = nowMillis + ttlMillis;
        Date exp = new Date(expMillis);
        builder.setExpiration(exp);
    }
 
    return builder.compact();
}
```


######Esa fue la pista, lo que vas a tener que ver, es que hacer con esto:

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJwaXN0YSI6IkxhIHBpc3RhIGVzICdlc3TDoSBtb2phZGEnIn0.IXbLz6xDeYGJHYfCVxUIVQB5fcAvrGg20BUNfvGZaBU
```


####Éxitos!  🚀
