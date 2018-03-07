# how to build a source jar

## 添加以下代码在要打的那个模块pom中

<code>
    <build>
            <resources>
                <resource>
                    <directory>src/main/resources</directory>
                    <includes>
                        <include>**/*</include>
                    </includes>
                </resource>
            </resources>
            <plugins>
                <plugin>
                    <artifactId>maven-compiler-plugin</artifactId>
                    <configuration>
                        <source>${java.version}</source>
                        <target>${java.version}</target>
                        <encoding>${project.build.sourceEncoding}</encoding>
                    </configuration>
                </plugin>
                <plugin>
                    <artifactId>maven-source-plugin</artifactId>
                    <executions>
                        <execution>
                            <id>attach-sources</id>
                            <goals>
                                <goal>jar</goal>
                            </goals>
                        </execution>
                    </executions>
                </plugin>
            </plugins>
        </build>
       
</code>