# How to Install Nginx on Debian

This guide provides step-by-step instructions for installing Nginx on a Debian system.

## Prerequisites

- A Debian-based system (Debian 10 Buster or later)
- Root access or a user with sudo privileges
- Terminal access

## Installation Steps

1. **Update System Packages**

   First, update your system's package index:

   ```
   sudo apt update
   ```

2. **Install Nginx**

   Install Nginx using the following command:

   ```
   sudo apt install nginx
   ```

3. **Start Nginx**

   After installation, Nginx should start automatically. To verify, run:

   ```
   sudo systemctl status nginx
   ```

   If it's not running, start it with:

   ```
   sudo systemctl start nginx
   ```

4. **Enable Nginx to Start on Boot**

   To ensure Nginx starts automatically on system boot:

   ```
   sudo systemctl enable nginx
   ```

5. **Adjust Firewall**

   If you're running a firewall, allow HTTP and HTTPS traffic:

   ```
   sudo ufw allow 'Nginx Full'
   ```

   This allows both port 80 (HTTP) and 443 (HTTPS).

6. **Verify Installation**

   Open a web browser and navigate to your server's IP address or domain name. You should see the default Nginx welcome page.
 The default Nginx page is served from the following directory:

**Ubuntu/Debian**: `/var/www/html/index.nginx-debian.html`. 

So to access the default page enter this on browser: `http://<server-ip>/index.nginx-debian.html`

Replace  `<server-ip>` with your Host IP Address

## Basic Nginx Management Commands

- Stop Nginx: `sudo systemctl stop nginx`
- Start Nginx: `sudo systemctl start nginx`
- Restart Nginx: `sudo systemctl restart nginx`
- Reload Nginx configuration: `sudo systemctl reload nginx`

## Configuration

The main Nginx configuration file is located at `/etc/nginx/nginx.conf`.

Site-specific configurations are typically stored in `/etc/nginx/sites-available/` and enabled by creating symlinks in `/etc/nginx/sites-enabled/`.

## Troubleshooting

- Check Nginx status: `sudo systemctl status nginx`
- View Nginx error logs: `sudo tail -f /var/log/nginx/error.log`
- View Nginx access logs: `sudo tail -f /var/log/nginx/access.log`

## Conclusion

You have successfully installed Nginx on your Debian system. For more advanced configurations and optimizations, refer to the [official Nginx documentation](https://nginx.org/en/docs/).
