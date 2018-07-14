# Introduction à spring boot + gradle

## Initialisation
Notes et traduction de https://spring.io/guides/gs/spring-boot/#scratch

* Initialisation du wrapper gradle:

```
gradle wrapper --gradle-version 4.8.1
```

* Creation de l'arborescence du projet:

```
mkdir -p src/main/java/hello
```

* src/main/java/hello/HelloControler.java

## Création d'une simple application web.

### Génération d'un contrôleur.

```java
package hello;

import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.bind.annotation.RequestMapping;

@RestController
public class HelloController {

    @RequestMapping("/")
    public String index() {
        return "Greetins from Spring Boot!";
    }
}
```
L'annotation `@RestController` associée à cette classe fait que cette
dernière est prête à être utilisé par Spring MVC pour répondre à
des requêtes web.

`@RequestMapping` lie l'url `/` à la méthode `index` de la classe. Tout
accès à cette méthode par un navigateur ou autre, une chaine de caractère
simple est retournée. Cela s'explique par le fait que `@RestController`
 combine les annoations `@Controller` et `@ResponseBody` ce qui fait que des données sont retournées plutôt que des vues en réponse à une
 requête web.

