# OCanada

This is where I keep my notes about setting up a VPN on AWS to watch MLB

Use the OpenVPN AMI from the AWS marketplace. This is the URL I used for the current version, 2.13.1, as of May 2024: https://aws.amazon.com/marketplace/server/fulfillment?ami=ami-0a14a0a5716389b2d&deliveryMethod=fe8020db-5343-4c43-9e65-5ed4a825c931&productId=fe8020db-5343-4c43-9e65-5ed4a825c931&ref_=cfg_full_continue&region=ca-central-1&version=14416e32-8aca-4b80-aaaf-3167480a07a0

From there, use the "Launch through EC2" option because that allows you to Auto-Assign a Public IP from the Network Settings pane. Right now, I am running a "t2.nano" instance which seems to work fine for this application. Using the "Launch from Website" option seems to default to no Public IP and that is a bummer to chase down based on their install instructions

The install instructions are pretty accurate as far as I remember. They get you through starting up the "Access Server". Currently, to make things work, TLS is disabled in the Admin GUI of the Access Server in the Advanced VPN tab under "TLS Control Channel Security". Get that set, download a config file, yoink the appropriate certs from the config and paste them into the relevant section of the router VPN services tab and you're off to the races.

Router Config:
