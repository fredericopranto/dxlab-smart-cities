
# Visualization of Big Urban Data

[2nd French-Brazilian School on Big Data and Smart Cities][school], Natal, 8-10 November 2017.


## Requirements
* [Mapbox][mapbox_dev] and [Google Maps][google_dev] API access tokens
* [Docker Community Edition][docker_ce] or [Docker Toolbox][docker_toolbox] (depending on your OS)
* Tutorial [material][dxlab] and [dataset][dxlab_ds]
* [Whiteboard][board] (for questions/answers during the tutorial) 


## Installation/Configuration

### Data Sience Lab Material (dxlab)

The material is divided in 2 parts:

* **[dxlab-smart-cities][dxlab]**: excercises and docker-configuration files.
* **[dxlab-smart-cities-ds][dxlab_ds]** (~30mb): dataset for the exercises. 

Download both parts. Unzip `dxlab-smart-cities-ds/data.zip` into `dxlab-smart-cities/notebook/data`.

> **IMPORTANT:**
> 
> + **dxlab-smart-cities-ds** is already available for download.
> + **dxlab-smart-cities** will be available the 1st day of the school.

### Access Tokens

The exercies use [Mapbox][mapbox_dev] and [Google Maps][google_dev] APIs. The APIs require an **access token/key** for use. Follow the instructions on each site for obtaining your tokens: 

* **Mapbox**: [Creating and managing access tokens][mapbox_token]
* **Google Maps**: [How to obtain and API Key][google_token]


### Docker

[Docker][docker_wiki] is a platform for creating and running containerized apps. You have 2 options for running docker:

+ **[Docker Community Edition][docker_ce]**. Ideal for recent Mac and Windows 10 Pro systems.
	* [Install Docker CE for Mac][docker_4mac]
	* [Install Docker CE for Windows][docker_4win]
+ **[Docker Toolbox][docker_toolbox]**. For older Mac and Windows systems that do not meet the Docker CE requirements.
	* [Install Docker Toolbox on Windows][docker_tool4win]
	* [Install Docker Toolbox on macOS][docker_tool4mac]


If you encounter one of the following error messages:

* VT-x/AMD-V hardware acceleration is not available on your system
* This host supports Intel VT-x, but Intel VT-x is disabled
* The processor on this computer is not compatible with Hyper-V

Follow this [instructions][guide_vtx] for enabling virtualization in your machine. For any other problems [google is your friend](http://www.giyf.com).


### Forwarding ports  

**_Only for Docker Toolbox Users_**

The exercises require to forward ports to the **default** virtual machine. Open Virtual Box and fordward the following ports ([how to forward ports](https://www.howtogeek.com/122641/how-to-forward-ports-to-a-virtual-machine-and-use-it-as-a-server/)):
 
* 8080:8080
* 4040:4040 


### Docker Dependencies

The tutorial depends on 2 docker images:

* **[jaeo/dxlab-smart-cities][image_dxlab]** (~2 gb). Contain jupyter, spark, python3, node + [python/node libraries][dxlab_deps].
* **[rabbitmq:3-management][image_rabbit]** (~125 mb). Contain RabbitMQ and RabbitMQ web UI.

These images are in a public repository. You can download them by opening a **Docker Quick Start Terminal** (or a clasical terminal if not running Docker Toolbox) and executing the following command:

`
$ docker pull jaeo/dxlab-smart-cities  rabbitmq:3-management
`

You can verify the existence of the images in your machine by executing:

`$ docker images`




[mapbox_dev]: https://www.mapbox.com/developers/
[google_dev]: https://developers.google.com/maps
[mapbox_token]: https://www.mapbox.com/help/how-access-tokens-work/
[google_token]: https://developers.google.com/maps/documentation/javascript/get-api-key
[dxlab_ds]: https://github.com/javieraespinosa/dxlab-smart-cities-ds
[dxlab]: https://github.com/javieraespinosa/dxlab-smart-cities
[school]: http://eventos.ifrn.edu.br/frbrschool
[docker_ce]: https://www.docker.com/community-edition
[docker_toolbox]: https://www.docker.com/products/docker-toolbox
[docker_wiki]: https://en.wikipedia.org/wiki/Docker_(software)
[docker_tool4mac]: https://docs.docker.com/toolbox/toolbox_install_mac/
[docker_tool4win]: https://docs.docker.com/toolbox/toolbox_install_windows
[docker_4mac]: https://docs.docker.com/docker-for-mac/install
[docker_4win]: https://docs.docker.com/docker-for-windows/install

[image_rabbit]: https://hub.docker.com/_/rabbitmq/
[image_dxlab]: https://hub.docker.com/r/jaeo/dxlab-smart-cities/ 
[dxlab_deps]: https://hub.docker.com/r/jaeo/dxlab-smart-cities/~/dockerfile/

[guide_vtx]: https://www.howtogeek.com/213795/how-to-enable-intel-vt-x-in-your-computers-bios-or-uefi-firmware/
[board]: https://docs.google.com/document/d/1zjw73GByBPQwVrLfRCOxXVuiGTsIVnhD5CP37U1DF1A/edit?usp=sharing


