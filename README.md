# uptime-kuma-monitoring
information about monitoring your applications with uptime kuma


### To set up uptime kuma on your server without using docker 
- make sure you have Node.js 18 / 20.4, npm 9, Git and pm2 (for running Uptime Kuma in the background) installed on your server
- then run;
```
git clone https://github.com/louislam/uptime-kuma.git
cd uptime-kuma
npm install
npm run setup
npm run build
pm2 install pm2-logrotate
pm2 start server/server.js --name "uptime-kuma"
pm2 save && pm2 startup
```

### To update
- run;
```
cd uptime-kuma

# Update from git
git fetch --all
git checkout 1.23.13 (or latest version) --force

# Install dependencies and prebuilt
npm install --production
npm run download-dist

# Restart
pm2 restart uptime-kuma
```

- then access uptime kuma on http://localhost:3001
