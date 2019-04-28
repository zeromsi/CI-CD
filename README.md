# Jenkins-CI-CD-pipeline
### CI/CD
Continuous integration (CI) and continuous delivery (CD) embody a culture, set of operating principles, and collection of practices that enable application development teams to deliver code changes more frequently and reliably. The implementation is also known as the CI/CD pipeline and is one of the best practices for devops teams to implement. CI/CD pipeline contains a set of instructions that runs defined software delivery/ deployment steps automatically. 
### Image 
Image is a complete blueprint of certain software product. It contains, program and needed libraries and binaries to run that program. 
### Container
Container is instance of an image. Every container is isolated process. It is possible to run n containers of an image. To create an instance of a particular image, we need a container runtime like docker, rocket. 
### Container runtime
In simple words a container runtime is a software that virtualize kernel of an operating system. A container gets code, binaries and libraries but no OS kernel from image recipe. But without OS kernel, it is not possible to run process. Here, a container runtime provides OS kernel to the container.
### Jenkins
Jenkins is a CI (continuous integration) server. It can schedule and run scripted pipeline. The open source community develops plugins for various kind of service. 
### Pipeline
A pipeline is a set of software deployment and delivery stages. 
### Complete CI/CD pipeline
![alt text](https://github.com/zeromsi/Jenkins-CI-CD-pipeline/blob/master/CI%252FCD%20Pipeline.png?raw=true)

### Installation (maven project)
1. Install ``` pipeline utility steps ``` plugin in jenkins
2. All Unit tests must run first. 
3. Unit test Suite will be like following,
```xml 
@RunWith(Suite.class)
@SuiteClasses({Basic.class,PayOrderServiceTest.class})
public class AllUnitTests {
	@BeforeClass
	public static void setUpClass() {
		  try {
	        	BufferedWriter writer = new BufferedWriter(new FileWriter("./jenkins/my.properties"));
				writer.write("BATCHID="+new Date().getTime());
				 writer.close();
			} catch (IOException e) {
				e.printStackTrace();
			}
	}

}
```
4. Add a file inside your ``` jenkinsFile ``` directory named as ``` my.properties ```
