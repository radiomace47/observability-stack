Welcome to my homelab observability stack repo! This is not finished. 
## Purpose
I wanted a way to monitor my home server. Right now, the stack runs on the machine it's operating on. This will eventually be migrated over to a Pi 5 or something similar. The goal is to monitor logs and system health, as well as get alerts when something goes awry.

I have also really worked hard to pare down these services to just what I need. The official documentation is very clearly geared towards enterprise level deployments, which I am not an enterprise, last I checked. 
## Design
Grafana is used as the graphical interface for the stack. Used for dashboards and the like.
Loki gathers my logs.
Prometheus gathers my metrics.
Alloy does Alloy things. It scrapes what it's told and ships it off to Loki and Prometheus and whoever else joins the party later on.
More to come.
**All of this is run with docker compose.**  
Ignore my Jellyfin and Flaresolverr stuff in my docker-compose file. I don't know where I want to put it yet, so it will live there for now. Pretend you don't see it. 
## Setup
Copy `.env.example` to `.env` in the same folder where your `docker-compose.yml` lives and update the paths for your system before running `docker compose up`. 
All my stuff currently just lives in a folder called `docker` and eventually will be split up so that my observability stuff has a home separate from my media server stuff. Tweak filepaths to your liking. 
Note that my `config.alloy` has a hardcoded Jellyfin log path that might not fit what you want. Just skim over filepaths. 
Also, this is all done on Linux. If you're running something else, expect a bit of leg work, I'm not sure how it would work there. 
