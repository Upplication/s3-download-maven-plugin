s3-download-maven-plugin
======================
Downloads a file or (recursively) the contents of a directory from S3.

Configuration parameters
------------------------

| Parameter | Description | Required | Default |
|-----------|-------------|----------|---------|
|bucketName|The name of the bucket|*yes*| |
|source|The source amazon s3 file key. Empty to download the whole bucket.|*no*| |
|destination|The destination file or destination folder. Directories *MUST* end with */*| *yes*| |
|accessKey|S3 access key | *no* | if unspecified, uses the Default Provider, falling back to env variables |
|secretKey|S3 secret key | *no* | if unspecified, uses the Default Provider, falling back to env variables |
|endpoint|Use a different s3 endpoint| *no* | s3.amazonaws.com |

Example: Download a bucket
----------------------
```xml
<build>
  ...

  <plugins>
    ...

    <plugin>
      <groupId>com.upplication.maven.plugins</groupId>
      <artifactId>s3-download-maven-plugin</artifactId>
      <version>1.0.2-SNAPSHOT</version>
      <executions>
        <execution>
            <phase>your phase</phase>
            <goals>
                <goal>s3-download</goal>
            </goals>
            <configuration>
                <bucketName>my-s3-bucket</bucketName>
                <!-- if you provide no source the whole bucket will be downloaded -->
                <destination>/my/local/dir/</destination>
                <accessKey>access key</accessKey>
                <secretKey>secret key</secretKey>
            </configuration>
        </execution>
      </executions>
    </plugin>
  </plugins>
</build>
```

