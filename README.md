# kecik
Zakikecik-kecik
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                      http://maven.apache.org/xsd/settings-1.0.0.xsd">

  <activeProfiles>
    <activeProfile>github</activeProfile>
  </activeProfiles>

  <profiles>
    <profile>
      <id>github</id>
      <repositories>
        <repository>
          <id>central</id>
          <url>https://repo1.maven.org/maven2</url>
        </repository>
        <repository>
          <id>github</id>
          <url>https://maven.pkg.github.com/OWNER/*</url>
          <snapshots>
            <enabled>true</enabled>
          </snapshots>
        </repository>
      </repositories>
    </profile>
  </profiles>

  <servers>
    <server>
      <id>github</id>
      <username>USERNAME</zakikecik>
      <password>TOKEN</mohdzaki1234@>
    </server>
  </servers>
</settings>
Authenticating with the GITHUB_TOKEN
If you are using a GitHub Actions workflow, you can use a GITHUB_TOKEN to publish and consume packages in GitHub Packages without needing to store and manage a personal access token. For more information, see "Authenticating with the GITHUB_TOKEN."

Publishing a package
By default, GitHub publishes the package to an existing repository with the same name as the package. For example, GitHub will publish a package named com.example:test in a repository called OWNER/test.

If you would like to publish multiple packages to the same repository, you can include the URL of the repository in the <distributionManagement> element of the pom.xml file. GitHub will match the repository based on that field. Since the repository name is also part of the distributionManagement element, there are no additional steps to publish multiple packages to the same repository.

For more information on creating a package, see the maven.apache.org documentation.

Edit the distributionManagement element of the pom.xml file located in your package directory, replacing OWNER with the name of the user or organization account that owns the repository and REPOSITORY with the name of the repository containing your project.

<distributionManagement>
   <repository>
     <id>github</id>
     <name>GitHub OWNER Apache Maven Packages</name>
     <url>https://maven.pkg.github.com/OWNER/REPOSITORY</url>
   </repository>
</distributionManagement
