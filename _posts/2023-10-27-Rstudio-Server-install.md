DOWNLOAD

# Download RStudio Server v2023.09.1+494

RStudio Server enables you to run the RStudio IDE you know and love on a Linux server, accessed from your web browser, bringing the power and productivity of the RStudio IDE to a centralized server-based environment.

Select Your Operating System:

Red Hat / CentOS

Debian / Ubuntu

SLES / OpenSUSE

Build from source

## Step 1: Select your server version 

Ubuntu 22

## Step 2: Install R

RStudio Server requires Debian version 10 (or higher) or Ubuntu version 18 (or higher). RStudio requires a previous installation of R version 3.3.0 or higher. To install the latest version of R you should first add the CRAN repository to your system.

[Debian Packages for R](https://cran.rstudio.com/bin/linux/debian/)

[Ubuntu Packages for R](http://cran.rstudio.com/bin/linux/ubuntu/)

YOU CAN THEN INSTALL R USING THE FOLLOWING COMMAND:



sudo apt-get install r-base



## Step 3: Install RStudio Server 

You may choose to verify the build's GPG signature prior to installing it.

TO DOWNLOAD AND INSTALL RSTUDIO SERVER OPEN A TERMINAL WINDOW AND EXECUTE THE FOLLOWING COMMANDS.



sudo apt-get install gdebi-core





wget https://download2.rstudio.org/server/jammy/amd64/rstudio-server-2023.09.1-494-amd64.deb





sudo gdebi rstudio-server-2023.09.1-494-amd64.deb



Size: 102.35 MB | 

SHA-256: C487A28B

 | Version: 2023.09.1+494 | Released: 2023-10-17