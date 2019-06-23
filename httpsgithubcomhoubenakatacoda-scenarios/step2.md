## Build the image

1. While inside the `myDir` folder, run following command:

	```
	time docker image build -t myPinger .
	```{{execute}}
	
	`time`, at the beginning of the command, is not necessary for the build. It will just show us how much time did the build take.
	
	The `-t` flag is to set the name of the final image, here we'll call it `myPinger`.
		
	**Note the dot** `.` at the end of the command, this is to set the build context, where Docker looks for the Dockerfile. In this case it's the current directory.
	
	If everything goes fine, you should see `Successfully tagged myPinger:latest` at the end of the output, in addition to the time taken by the build process.
	
2. Now run the same build command again, and notive how fast is the build!

	Comapre the time of the first build attempt with the second one.
	
	> Question: What do you think has made the build much faster the second time?
	
	If you check the output of the build command, you'll see several times `---> Using cache`. Layers that have been built before, are just reused! We will talk about caching in more detail in a more advanced chapter.
	

