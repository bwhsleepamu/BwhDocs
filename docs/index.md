# Overview of Things Done/To Do

## TODO Lists

### Server Setup for Access and Kdt_Output_Stripper
- [x] Set up Shiny proxy + authentication
- [x] Update mounted drive access
- [x] Upgrade RVM
- [x] Upgrade Ruby
- [x] Upgrade Gems
- [x] Upgrade Passenger
- [x] Upgrade Access to branch 1.1.0
- [ ] Re-configure SSL
- [ ] Ensure SSL-only access to both shiny sites and main Rails sites
- [ ] Fix LDAP oauth flow for Partners logins
- [ ] Allow Access to run on SSL and KDT tool to run at the same time

### Tasci Merger
- [x] Update core code with recent mappings
- [ ] Release new version of gem with updated inputs
- [ ] Refactor Access and extract Tasci merger app into a self-contained Rails app
- [ ] Test on Tasci Locations on T, I, and X drives

### Access to Database and Data Requests
- [ ] Ensure Scott/Beth Partners accounts allow login to Access
- [ ] Determine location of data requested by John: database vs. files
- [ ] Download and compile database data for John
- [ ] Train Scott on use of Access tool for DB data downloads (and possibly revamp tool)



## Shiny Apps and Server Setup

### Resources
1. https://weihanglo.gitbooks.io/debian-server-for-r-computing/content/doc/other_nginx.html
2. http://docs.rstudio.com/shiny-server/
3. https://www.r-bloggers.com/add-authentication-to-shiny-server-with-nginx/
4. https://github.com/sleepepi/sleepepi/tree/master/virtual-machines
5. https://wiki.centos.org/TipsAndTricks/WindowsShares

The root for these apps is `/srv/`

The configuration file for shiny server is at:
```
/etc/shiny-server/shiny-server.conf
```

`scott kdttime`
`beth tascitime`

### Ruby Apps
The NGINX configuration can be found at `/usr/local/nginx/config`

### Work Log
Logged into `dsm2.dipr.partners.org`. This VM holds the NGINX and the Shiny Servers.

I need to figure out how to allow both Shiny and Ruby apps to run on the server.

1. Set up Shiny with authentication using this source: https://www.r-bloggers.com/add-authentication-to-shiny-server-with-nginx/
  a. Modified NGINX config to re-route /kdt/ requests to the Shiny port
  b. Modified Shiny Server config to only allow port access from localhost

2. Lots of RVM/Ruby/Gem/Passenger etc. updates
```
  passenger_root /PHShome/pwm4/.rvm/gems/ruby-2.1.1/gems/passenger-4.0.41;
  passenger_ruby /PHShome/pwm4/.rvm/wrappers/ruby-2.1.1/ruby;
```

3. Updated Ruby and Passanger. Had to re-configure NGINX. Followed setup from https://github.com/sleepepi/sleepepi/tree/master/virtual-machines. Integrated both Shiny and Normal webserver.

After setting everything up, ran into problems with SSL access to the ruby app. Received a 503 error for no reason.

4. Windows share mounts: https://wiki.centos.org/TipsAndTricks/WindowsShares
(These need to be updated periodically)

## Sleep Structure Manuscript

### TODO List
- [ ] Examine definitions of circadian day / circadian night, comparing to Beth's email. Update figures accordingly
- [ ] Update Figure 7
  * [ ] Put boxes around panels and label them a-d
  * [ ] Make font larger on all axes + label Y axis
  * [ ] Additional changes from comments in manuscript file
  * [ ] Create version of Figure 7 for supplemental which includes comparison of circ day vs. circ night.
- [ ] Create 2nd Version of figure 8 with comparison of circadian day/night.
- [ ] Select either figure 5 or figure 6 to go in the main paper. Update the figure to better-illustrate the desired message (which is?)
- [ ] Combine figures 2/3 into one figure with different panels. Look at comments in manuscript for further details.  
- [ ] Verify target journal
- [ ] Set target submission date!
Another version of of figure 8:

### Andrew and Beth thoughts 3/24/2017

#### Two sources of novelty
- Looking at sleep structure Forced Desynchrony protocols
- Finding wrt. what awakenings do to the structure of the sleep/wake NREM/REM cycle
  especially figure 8.

#### Figures
Many of the figures currently in the manuscript will move to supplemental material.

The figures that will be the focus of the main manuscript are:
1. Figure 7
2. Figure 5 or Figure 6 or Improved version.
3. Figure 2/3 --> Figure 2a/2b

Supplemntal material:
1. Figure 1 - Sequence Length Histograms
2. Figure 4 - State transition heatmaps: need to be updated to better-highlight the interesting aspects.
3. Figure 5 or 6?

Unsure:
1. Figure 9?
