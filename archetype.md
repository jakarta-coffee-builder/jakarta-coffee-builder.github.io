* TOC
{:toc}

# Jakarta EE Essentials Archetype 
![Maven Central Version](https://img.shields.io/maven-central/v/com.apuntesdejava/jakarta-ee-essentials)
![Maven Central Last Update](https://img.shields.io/maven-central/last-update/com.apuntesdejava/jakarta-ee-essentials) 
[![GitHub](https://img.shields.io/badge/maven-archetype-darkgreen?logo=github)](https://github.com/jakarta-coffee-builder/jakarta-ee-essentials)


With this archetype, you can create a Jakarta EE project with minimal dependencies and configurations.

This will allow you to have a clean and clear `pom.xml` file so you can add more configurations as needed.


### Usage

To create a new Jakarta EE project using this archetype, run the following command:

```shell
mvn -DarchetypeGroupId=com.apuntesdejava \
    -DarchetypeArtifactId=jakarta-ee-essentials \
    -DarchetypeVersion=__ARCHETYPE_VERSION__ \
    -DjakartaProfile={jakartaProfile} \
    -DjakartaModule={jakartaModule} \
    -DjakartaVersion={jakartaVersion} \
    org.apache.maven.plugins:maven-archetype-plugin:generate 
```

Values for `jakartaProfile` property:
- `core`
- `web`
- `full` (default)

Values for `jakartaModule` property:
- `ejb`
- `web` (default)


Values for `jakartaVersion` property:
- `10.0.0`
- `11.0.0` (default)

### 📌 Note
As of this post, it is only creating the dependency for Jakarta EE 11, version 11.0.0

### Example

```shell
mvn -DarchetypeGroupId=com.apuntesdejava \
    -DarchetypeArtifactId=jakarta-ee-essentials \
    -DgroupId=com.example \
    -DartifactId=example-app \
    -Dversion=1.0.0-SNAPSHOT \
    -DarchetypeVersion=__ARCHETYPE_VERSION__ \
    -DjakartaProfile=core \
    -DjakartaVersion=11.0.0 \
    org.apache.maven.plugins:maven-archetype-plugin:generate 
```


### Showing
[![asciicast](https://asciinema.org/a/VybSbO8RQKmQQhSrTkMxcUzeI.svg)](https://asciinema.org/a/VybSbO8RQKmQQhSrTkMxcUzeI)

<script>
(() => {
  const placeholder = '__ARCHETYPE_VERSION__';
  const metadataUrl = 'https://search.maven.org/solrsearch/select?q=g:%22com.apuntesdejava%22%20AND%20a:%22jakarta-ee-essentials%22&rows=1&wt=json';

  fetch(metadataUrl)
    .then((response) => response.ok ? response.json() : Promise.reject(response))
    .then((metadata) => {
      const version = metadata.response.docs[0].latestVersion;

      document.querySelectorAll('code').forEach((code) => {
        code.textContent = code.textContent.replaceAll(placeholder, version);
      });
    })
    .catch(() => {
      document.querySelectorAll('code').forEach((code) => {
        code.textContent = code.textContent.replaceAll(placeholder, '0.0.7');
      });
    });
})();
</script>
