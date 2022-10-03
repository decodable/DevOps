# Create base image from disk
1. Install OS from disk. 
   - This can be done by installing OS on a virtual machine via ISO disk image.
   - For redhat, kickstart can help to make the installation process automatically
2. Export the virtual machine into .OVA file as backup
3. Using tar to create a full image of existing system
4. import the image

# References
1. [How to make docker image of host operating system which is running docker itself?](https://stackoverflow.com/questions/26742967/how-to-make-docker-image-of-host-operating-system-which-is-running-docker-itself)
2. [Create a base image](https://docs.docker.com/develop/develop-images/baseimages/)
