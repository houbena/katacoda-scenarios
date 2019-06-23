The first step consists of writing a Dockerfile, that we will use later to build our container image.

1. It's a best practice to create your Dockerfile inside an empty directory then copy into it only what the build needs.
	
	So let's start by creating a folder `myDir`, and `cd` into it:

	`mkdir myDir; cd myDir`{{execute}}

2. Create a file `Dockerfile`:
	
	`touch Dockerfile`{{execute}}

	In the editor view, click on `myDir` to expand its content, then click on `Dockerfile` to open it. 

	Paste following content to the Dockerfile: 

	<pre class="file" data-filename="Dockerfile" data-target="replace">
	FROM ubuntu
	RUN apt-get update && apt-get install -y iputils-ping 
	CMD ping -c 5 8.8.8.8
	</pre>
	
	> Question: Looking at this Dockerfile, what will be the base image of our final image?
	
	If you say: it's `Ubuntu`! You got it right. And if you guessed the `latest` tag, you're even righter. You can see tags as versions. Since we didn't specify any tag after the image name, `latest` is picked. Don't worry if you never heard of *tags*, we will talk about this image property in a more advanced topic.

	The second line of the Dockerfile will execute an update of `apt-get`, the package manager, then install the ping tool.
	
	The final line of the Dockerfile sets a default command to the final image. This default command is not executed during the image build, but rather when a container is launched based on the final image. We'll see this in action in a minute.

