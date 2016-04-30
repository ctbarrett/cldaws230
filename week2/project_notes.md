# CLDAWS230 Final Project - Craig Barrett, Winter 2016

## Overview

For a final project, my plan is to build a blog hosting infrastructure using Wordpress for the CMS, and either MySQL or
Aurora (via RDS) for the backend database. I will also try to include distributed caching layers (cloudfront &
elasticache) in front of both the web and database tier, as well.

Time and resources permitting, my overly ambitious plan is to also include some additional supporting infrastructure
and automation components like a Chef server for managing EC2 compute instances (though I may decide to use OpsWorks,
instead), an OpenVPN solution for secure remote access and ensuring privacy when working over open wifi hotspots or
other untrusted networks, and Code Pipeline / Code Deploy for automated deployments.

## Wordpress cluster

The Wordpress cluster will be fronted by a multi-AZ ELB, will use CloudFront for a CDN, and an auto-scaling group for
deployments and scaling in response to increasing load. I would also like to configure Route53 to facilitate canary
testing and/or blue/green deployments. The backend database will use RDS with either MySQL or Aurora, to support the
multi-AZ configuration.

## Cross-region failover

Initially, my target will be to replicate the infrastructure in a failover region through OpsWorks & Cloudformation.
Ultimately I will work on handling data persistence, most likely through backups to an S3 bucket that is replicated to
the failover region, but I may also do an active-active configuration, that just needs to promote a read-replica of the
database in the event of a failover.
