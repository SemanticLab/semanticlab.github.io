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

