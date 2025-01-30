[English](/README.md) | [Persian](/README-Fa.md)

------------------------------------------
<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./Media/Pic.png">
    <img alt="6to4" src="./Media/Pic.png">
  </picture>
</p>


<h2 align="center"><strong>6TO4 Tunnel - Private IP (Multiple SERVERS)
  <br>
(Tunnel Between 5 Foreign Servers and 1 in Iran, and Vice Versa)
</strong></h2>

<br>

[![](https://img.shields.io/github/v/release/Azumi67/6TO4-PrivateIP_multipleSERVERS.svg)](https://github.com/Azumi67/6TO4-PrivateIP_multipleSERVERS/releases)
[![Downloads](https://img.shields.io/github/downloads/Azumi67/6TO4-PrivateIP_multipleSERVERS/total.svg)](#)
[![License](https://img.shields.io/badge/license-GPL%20V3-blue.svg?longCache=true)](https://www.gnu.org/licenses/gpl-3.0.en.html)

> **Disclaimer:** This project is only for personal learning and communication, please do not use it for illegal purposes, please do not use it in a production environment

<br>

## 🔧 Install & Upgrade

```
apt install curl -y && bash <(curl -Ls https://raw.githubusercontent.com/Azumi67/6TO4-PrivateIP_multipleSERVERS/main/6to4.sh --ipv4)
```

<br>

## **🌟 Features**  

- Create a 6to4 tunnel between multiple servers [Anycast] & [PrivateIP]  

- Tunnel between 5 foreign servers and 1 Iranian server, and vice versa  

- Ability to use the IP on other servers (not recommended) [Anycast]  

- Uses `cronjob` instead of `service`  

- Ability to delete tunnels  

- After setting up this tunnel, you can use the generated IPs for the main tunnel or port forwarding  

- Compatible with load balancing in FRP  

- Ability to create multiple private IPs for your servers  

 
<br>

##  💡 Tips

<details>
  <summary>Click For Tips</summary>

1. **Configure Foreign Servers First**  
   - Start by configuring your foreign servers first, then configure the Iranian server.

2. **Tunnel Between 5 Foreign Servers and 1 Iranian Server**  
   - You can create a tunnel between 5 foreign servers and 1 Iranian server, and vice versa.

3. **Use of Private IPs for Load Balancing**  
   - These private IPs can be used for load balancing, which I will provide soon.

4. **Fixing Ping Issues Between Servers**  
   - If pinging between the 5 foreign servers and 1 Iranian server does not work while creating the tunnel, reboot all the servers at once. This should likely fix the issue.

5. **Alternative Solution for Connection Issues**  
   - If there is a specific server connection issue (e.g., in the 5 foreign server and 1 Iranian server tunnel, server 3 is the problem), uninstall the problematic server and reconfigure it.

6. **Ensure Correct Use of IPs**  
   - Ensure that you use the correct IP for each server to avoid errors.
   - For example, when configuring foreign server 1 and the Iranian server, you should use the Turkish server’s IP for foreign server 1, and use the German server’s IP for foreign server 2 and the Iranian server.

7. **SSH or Ping from Iranian Server to Foreign Servers**  
   - Before setting up the 6to4 tunnel, make sure you can SSH or ping from the Iranian server to the foreign servers.

8. **Private IPs for Each Foreign Server**  
   - In the Iranian server configuration, you will have a unique private IP for each foreign server. Ensure these IPs are entered correctly.

9. **If the Tunnel is Panel-to-Panel**  
   - For panel-to-panel tunnels, only the foreign server’s IP is required.

10. **If FRP Tunnels Are Used**  
    - For FRP tunnels, you will need the private IPs of each foreign server on the Iranian server.

11. **Open Private IPs**  
    - If the tunnel is panel-to-panel, you will need to open the private IPs.

12. **Testing and Error Correction for Tunnel Configuration**  
    - Through trial and error, you can configure the tunnels correctly.
</details>

  <br>

  
##  📜 How To Use Script

<details>
  <summary>Click For Usage Instructions</summary>
  
  ### 🛠 Creating a Private IP Between 1 Foreign Server and 1 Iranian Server
  <details>
    <summary>Click For Details</summary>
    
  > ![6TO4-1-1](./Media/1-1.png)

      - Create a private IP: Start from the foreign server.  
      - Enter the IPv4 addresses of both the foreign and Iranian servers.  
      - Enter the /64 subnet.  
      - Specify the number of private IPs you need.  
      - Save the generated IPs in Notepad for use in the tunnel.  
      - The private IP and a ping service will be automatically created to prevent disruptions.  
      - Repeat the same steps for the Iranian server.  

  </details>

  <br>

  ### 🛠 Creating a Private IP Between 1 Foreign Server and 5 Iranian Servers
  <details>
    <summary>Click For Details</summary>

  > ![6TO4-1-1](./Media/1F-5IR-F.png)

    🌍 Foreign Server Configuration

    - In this tunnel, we use 2 Iranian servers and 1 foreign server.  
    - Always start the tunnel configuration from the foreign server.  
    - Enter the number of Iranian servers you have (the maximum allowed is 5 servers).  
    - For each Iranian server, enter the same foreign IP (e.g., Turkey).  
    - Note: If you use the Yerevan IP for Iranian server 1, use the same Yerevan IP for the configuration of Iranian server 1.  
    - For example, if you use the Yerevan IP for server 1 and the Shatel IP for server 2, then in the Iranian server configuration, server 1 will use the Yerevan IP and server 2 will use the Shatel IP. Otherwise, the tunnel won't be established.  
    - Enter the number of IPs you need for each server.  
    - To create cronjobs for your servers, enter the number of servers with a space in between. For example, if you have 2 Iranian servers, enter it as (2 1).  

    ---

> ![6TO4-1-1](./Media/1F-5IR-IR1.jpg)

    🇮🇷 Iranian Server 1 Configuration

    - Now, we need to configure each Iranian server separately.  
    - For example, if for Iranian server 1, we used the Yerevan server IP (from the previous image), then we need to use the Yerevan IP here as well for Iranian server 1.  
    - The foreign server IP remains the same for all Iranian servers since the tunnel involves 3 Iranian servers and 1 foreign server.  
    - Enter the number of IPs you want for this server.  

    ---

> ![6TO4-1-1](./Media/1F-5IR-IR2.jpg)

    🇮🇷 Iranian Server 2 Configuration

    - For Iranian server 2, configure it as explained for Iranian server 1.  
    - The foreign server IP is the same for all Iranian servers.  
    - Enter the number of IPs you need for this server.  
    - If you have a third Iranian server, configure it in the same way as the previous servers.  
    - To remove tunnels, go to the relevant section to delete the tunnel.  

  </details>

  <br>

  ### 🛠 Creating a Private IP Between 5 Foreign Servers and 1 Iranian Server
  <details>
    <summary>Click For Details</summary>

  > ![6TO4-1-1](./Media/5F-1IR-F1.png)

    🌍 Foreign Server Configuration

    - Always start the tunnel configuration from the **foreign server**.  
    - Now, we need to configure each foreign server separately.  
    - The Iranian server is the same for all foreign servers, since the tunnel involves 3 foreign servers and 1 Iranian server.  
    - Enter the number of IPs you want for each foreign server.

    ---

  > ![6TO4-1-1](./Media/5F-1IR-F2.png)

    🌍 Foreign Server 2 Configuration

    - For foreign server 2, configure it similarly as you did for foreign server 1.  
    - The Iranian server is the same for all foreign servers.  
    - Enter the number of IPs you want for this server.  
    - If you have a third foreign server, configure it as shown in the example.  
    - To remove tunnels, go to the relevant section and delete the tunnel.  


    ---

  > ![6TO4-1-1](./Media/5F-1IR-F2.png)

    🇮🇷 Iranian Server Configuration

    - This tunnel uses 2 foreign servers and 1 Iranian server.  
    - Enter the number of foreign servers you have (the maximum allowed is 5 servers).  
    - For each foreign server, enter the same Iranian IP (e.g., Yerevan) and specify the foreign server IP for each server.  
    - Note: If you enter the Turkey IP for foreign server 1, use the same Turkey IP for the configuration of foreign server 1.  
    - This means that if you use the Turkey IP for server 1 and the Germany IP for server 2, the configuration of the foreign servers will also have Turkey IP for server 1 and Germany IP for server 2, otherwise, the tunnel will not be established.  
    - Enter the number of IPs you need for each foreign server.  
    - To create cronjobs for your servers, enter the number of servers with a space in between. For example, if you have 2 foreign servers, enter it as (2 1).  

  </details>
</details>


<br>
 

## **🌐 6 TO 4 Tunnel Types** 
<details>
  <summary>Click for Tunnel Details</summary>
  
  ### **❌ Tunnel Without Anycast**  
  <details>
    <summary>Click For Details</summary>

  > ![6TO4-1-1](./Media/T-WO-F.png)

    🌍 Foreign Server Configuration
    
    - This tunnel uses one foreign server and one Iranian server.  
    - Start the tunnel configuration from the **foreign server**. Enter both the foreign and Iranian server IPs.  
    - Specify the number of IPs you need.  
    - To enable the ping service, enter the **IPv4 address of the Iranian server** as shown in the screenshot.  
    
    ---

  > ![6TO4-1-1](./Media/T-WO-IR.png)

    🇮🇷 Iranian Server Configuration

    - This tunnel uses one foreign server and one Iranian server.  
    - Enter both the foreign and Iranian server IPs.  
    - Specify the number of IPs you need.  
    - To enable the ping service, enter the **IPv4 address of the foreign server** as shown in the screenshot.  

  </details>

  <br>

  ### **✅ Tunnel with Anycast**  
  <details>
    <summary>Click For Details</summary>

  > ![6TO4-1-1](./Media/T-W-F.png)

    🌍 Foreign Server Configuration

    - This tunnel uses one foreign server and one Iranian server.  
    - Start the tunnel configuration from the **foreign server**. Enter the foreign server IP.  
    - Specify the number of IPs you need.  
    - To enable the ping service, enter the **IPv4 address of the Iranian server**.  
    - You can use this IP on other servers as well and get a ping, but the ping time depends on your server and may not be optimal.  
    
    ---

  > ![6TO4-1-1](./Media/T-W-IR.png)

    🇮🇷 Iranian Server Configuration

    - This tunnel uses one foreign server and one Iranian server.  
    - Enter the **IPv4 address** of the Iranian server.  
    - Specify the number of IPs you need.  
    - To enable the ping service, enter the **IPv4 address of the foreign server**.  
    - You can use this IP on other servers as well and get a ping, but the ping time depends on your server and may not be optimal.  

  </details>
</details>

<br>

## 👀 Preview  
<details>
  <summary><strong>📷 Click to Expand Screenshots</strong></summary>
  <br>

  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./Media/Screenshot1.png">
    <img alt="6TO4-SS1" src="./Media/Screenshot1.png">
  </picture>

  <br>

  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./Media/Screenshot2.png">
    <img alt="6TO4-SS2" src="./Media/Screenshot2.png">
  </picture>

  <br>
</details>

<br>

## 🙏 A Special Thanks to

- [Amir SPB](https://github.com/AMiR-SPB/) For Create README Files


<br>
  
## **💻 Useful Scripts**  
> - These Scripts are Optional.  


#### OP Iran Script
```bash
apt install curl -y && bash <(curl -s https://raw.githubusercontent.com/opiran-club/VPS-Optimizer/main/optimizer.sh --ipv4)
```

#### Hawshemi Script
```bash
wget "https://raw.githubusercontent.com/hawshemi/Linux-Optimizer/main/linux-optimizer.sh" -O linux-optimizer.sh && chmod +x linux-optimizer.sh && bash linux-optimizer.sh
```

#### Add an Additional IPV6 Address
```bash
bash <(curl -s -L https://raw.githubusercontent.com/opiran-club/softether/main/opiran-seth)
```

<br>

## **💬 Telegram :** 

🆔 [OP Iran GP](https://t.me/OPIranClub)

<br>

## **📂 Source :**
<details>
  <summary><strong>Click to See</strong></summary>
 
  ### 1️⃣ [OP Iran](https://github.com/opiran-club)
  ### 2️⃣ [Hwashemi](https://github.com/hawshemi/Linux-Optimizer)
  
  <br>
</details>

<br>

## **📺 Tutorial :**
<details>
  <summary><strong>Click to Watch Tutorial Videos</strong></summary>
 
  ### 1️⃣ [YouTube](#)

<br>
</details>

------------------------------------------
