<style>
  .responsive-container {
	position: relative;
	padding-bottom: 53.25%;
	padding-top: 30px;
	height: 0;
	overflow: hidden;
}
.responsive-container,
	.responsive-container iframe {
	max-width: 1280px;
	max-height: 720px;
}
.responsive-container iframe {
	position: absolute;
	top: 0; left: 0;
	width: 100%;
	height: 100%;
}
</style>

## Wikibase Install Basic Tutorial

<div class="responsive-container">
<iframe width="100%" height="720" src="https://www.youtube-nocookie.com/embed/a3wM4Xd3BKI?VQ=HD1080" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


*Below is a barebones version of the tutorial which provides commands you can copy and paste.*

### Step 1
### Setting up server. 

We are using Digitalocean.com for this tutorial. If you want to use it you need to setup an account: https://www.digitalocean.com/ 

Create a new droplet with the green Create button

Select CoreOS from the container distribution tab:

![Select CoreOS](https://raw.githubusercontent.com/SemanticLab/semanticlab.github.io/master/assets/howto/wikibase_os_select.png)

We are going to use the $20 a month 4 GB / 2 CPUs / 80 GB SSD disk / 4 TB transfer server
Pick a region near you, I’m using NYC 3

We need to attach an SSH key to be able to log into the server. If you don’t have one click New SSH Key button and follow the directions, I show how to do it on OSX in the video.

Once the blue bar fills up and the server is online click the ipv4 label to copy the IP address to the clipboard.

SSH to host - In Terminal or Windows SSH or Putty we are going to SSH to the host. For me on OSX I open Terminal and run:

`ssh -i /Users/thisismattmiller/.ssh/wikibase core@167.99.125.251`

I am saying use this SSH key and use the username “core” to log into my server’s IP address

It might prompt you to accept and then you should see:

`Container Linux by CoreOS stable (2191.4.1)`

### Step 2 
### git clone the repos and install docker-compose and run

Once we are logged in we want to clone two repositories so we try:
```
git clone https://github.com/wmde/wikibase-docker.git
cd wikibase-docker
git clone https://github.com/SemanticLab/wikibase-basic-local.git
```


This clones the two repos we need, the wikibase docker images and my repo of support files.

We need to install docker-compose so we run:
```
chmod +x wikibase-basic-local/install_compose.sh
sudo ./wikibase-basic-local/install_compose.sh
```


This makes the install script executable and then we run it as root, it install docker-compose

Now we just run:
`docker-compose up`

This will download the docker images and start them running, will take a few min.

### Step 3
### Test and gather some data

Once things stop scrolling and it says something like:
```
wdqs-updater_1     | 17:28:25.748 [main] INFO  o.w.q.r.t.change.RecentChangesPoller - Got no real changes
wdqs-updater_1     | 17:28:25.748 [main] INFO  org.wikidata.query.rdf.tool.Updater - Sleeping for 10 secs
```

Your wikibase should be running at:

`http://<YOUR-IP>:8181`

So for mine it was http://167.99.125.251:8181

The services run of different ports

The first thing we need to do it create some data because I’ve found things stop working if you restart the service after it has initialized but has no data (seems like it break wdqs-updater)

Click on special pages on the left and create a property and an item:

![Add Data](https://raw.githubusercontent.com/SemanticLab/semanticlab.github.io/master/assets/howto/wikibase_basic_add_data.gif)


We also need to make an OAuth key to use with Quickstatments:
Make sure you are Logged In
Click Special pages
OAuth consumer registration
Request a token for a new consumer.

![Fill out Oauth Form](https://raw.githubusercontent.com/SemanticLab/semanticlab.github.io/master/assets/howto/wikibase_basic_create_oauth.gif)

Fill out the form, important values:
OAuth "callback" URL: “http://<YOUR-IP>:9191/api.php”
Allow consumer to specify a callback in requests and use "callback" URL above as a required prefix. : Yes
Rights: High-volume editing, Edit existing pages, Edit protected pages, Create, edit, and move pages

Make sure you copy the key and secret, looks like this: You have been assigned a consumer token of 978b1226ab40cd643c5a9041039b85c1 and a secret token of 6186cbbfa24d13bf4df68713a7ada045a6adb4e1. Please record these for future reference.

Now we need to approve the key, click:

Special pages -> Manage OAuth consumers -> Queue of proposed consumer requests \[1\] -> review/manage 
And then “Update consumer status”

![Approve OAuth](https://raw.githubusercontent.com/SemanticLab/semanticlab.github.io/master/assets/howto/wikibase_basic_auth_oauth.gif)



