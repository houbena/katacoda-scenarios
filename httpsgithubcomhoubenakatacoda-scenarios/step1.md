## Writing the Dockerfile

1. Create an empty directory `myDir`, and `cd` into it:

	`mkdir myDir; cd myDir`{{execute}}

2. Create a file `Dockerfile` (with `D` uppercase), and paste following content:

	```
	FROM ubuntu
	RUN apt-get update && apt-get install -y iputils-ping 
	CMD ping -c 5 8.8.8.8
	````{{execute}}
	
	> Question: Looking at this Dockerfile, what will be the base image of our final image?
	
	If you say it's `Ubuntu`, you got it right. And if you guessed the `latest` tag, you're even righter. You can see tags as versions. Since we didn't specify any tag after the image name, `latest` is picked. Don't worry if you never heard of *tags*, we will talk about this image property in a more advanced topic.

	The second line of the Dockerfile will execute an update of `apt-get`, the package manager, then install the ping tool.
	
	The final line of the Dockerfile sets a default command to the final image. This default command is not executed during the image build, but rather when a container is launched based on the final image. We'll see this in action in a minute.

