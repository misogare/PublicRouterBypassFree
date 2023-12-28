# PublicRouterBypass

A free solution for hosting local machine projects on a domain, bypassing the need for router access or port forwarding. This repository includes a simple system architecture that integrates with previous projects, offering a seamless experience for sharing resources from your local machine to the outside world.

## System Architecture Hosting on Local Host with CI/CD Pipeline (Shared Environment)

We had a team of 3 developers working on a .NET project and 2 others on a Kotlin Android app. We needed to host both the app and website locally without router access. Here’s how we achieved it:

### Steps:
1. **GitHub Repositories:**
   - Connected all projects to GitHub; one repo each for the app and website, enabling a shared working environment.

2. **Automation & Monitoring:**
   - Utilized OneDrive and tools like Argo CD or Jenkins to automate and monitor files across both projects.

3. **External Hosting with Ngrok:**
   - Implemented Ngrok’s free plan to host contents externally, accessible via a domain like `2742-140-159-2-226.ngrok-free.app`.

4. **Domain Customization with Cloudflare:**
   - Enhanced monitoring capabilities and connected to our custom domain using Cloudflare’s free access.

### Notes:
- Alternative to OneDrive, CI/CD tools like Argo CD or Jenkins can be used especially when integrating microk8s or any local Kubernetes container.
- The key to bypassing public router restrictions lies in utilizing services like Ngrok for external hosting.
### System Arch:
  ![system arch](https://github.com/misogare/PublicRouterBypassFree/assets/130363781/20f92fd4-a00d-426e-bb68-05e6b0fd6aad)

### Ngrok Tunneling Steps:
1. Create an account for free.
2. Download the Ngrok app.
3. Run Ngrok, add your authentication.
4. Execute script in CMD environment `ngrok http 8080` (if your application is running on localhost:8080) to broadcast it externally.
5. Copy the provided domain and test it in any browser.

### Cloudflare Tunneling Steps:
1. Connect your domain to Cloudflare if you have one.
2. Go through either page forwarding or tunneling process as per requirement (page forwarding used in this scenario).
3. For page forwarding, paste the ngrok domain under rules/pages section in Cloudflare dashboard then select ‘Forwarding URL’, ‘302 Temporary Redirect’.

## Additional Information
This setup was designed to work with a team of developers working on different aspects of the project. The .NET project was handled by three developers while the Kotlin Android app was managed by two developers. The goal was to host the app and website on a local machine without having access to the router. 

The architecture was designed with simplicity and efficiency in mind, using readily available tools and services. It allows for real-time collaboration, automated deployment, and external hosting of local projects. 

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
