# Facktory demo with Node

Code borrowed from https://www.mikeperham.com/2019/01/16/using-faktory-with-javascript/
with usage in Ubuntu 18.04 64 bits

## Install

    wget https://github.com/contribsys/faktory/releases/download/v0.9.5-1/faktory_0.9.5-1_amd64.deb
    sudo dpkg -i faktory_0.9.5-1_amd64.deb

Username is `helloworld` and password is generated initialy by default in `/etc/faktory/password`

## Run the demo

    # Project copy
    git clone https://github.com/webgeodatavore/faktory-with-javascript
    cd faktory-with-javascript

    # Install deps (supposing you already have Node)
    npm install

	# Install foreman (you must have Ruby installed)
	sudo gem install foreman

Faktory runs as a service on Linux e.g `sudo service faktory status` so contrary to original post, we don't need to run faktory in the `Procfile`


    # 450585c9bf9545f4 is the password from `/etc/faktory/password`.
    # You need to change it according to output from `cat /etc/faktory/password`
    # Run to provide the password
    FAKTORY_URL="tcp://helloworld:450585c9bf9545f4@localhost:7419" foreman start

You will see an output.

You can also open http://localhost:7420 and type username and password to see the dashboard

## Credits

* Mike Perham
* Thomas Gratier (myself) for the review and adaptation to Linux
