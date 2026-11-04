*This project has been created as part of the 42 curriculum by mgerard.*

# NetPractice

## Description

**NetPractice** is a general practical exercise designed to introduce the basics of **computer networking**. The goal of the project is to configure small-scale, simulated networks so that they work properly: assigning valid **IP addresses**, choosing correct **subnet masks**, connecting devices through **routers**, and setting up **default gateways** and routing tables.

The networks are not real: they are simulated and displayed through a training interface that runs in a web browser. For each of the 10 levels, a non-functioning network diagram is shown, along with one or more objectives (e.g. "host A must be able to communicate with host B"). The task is to modify the editable fields (IP addresses, masks, routes) until every goal is reached.

Overview of what is practiced:

- Understanding how TCP/IP addressing works (network address, host range, broadcast address).
- Choosing and reading subnet masks (dotted decimal and CIDR notation).
- Making sure devices that must talk directly share the same subnet.
- Configuring routers and routing tables (destination => next hop, default route `0.0.0.0/0`).
- Using the interface logs to diagnose problems (invalid IP, missing gateway, no matching route, etc.).

## Instructions

### Running the training interface

1. Download the archive attached to the project's page and extract it into any folder.
2. In this folder, run the launch script:

   ```sh
   ./run.sh
   ```

   This starts a local web server and opens your default web browser on the NetPractice page.

3. If `run.sh` does not work, start the server manually (the port number can be changed):

   ```sh
   python3 -m http.server 49242
   ```

   Then open `http://localhost:49242` in your web browser.

4. In the interface, go to the **Training** tab and **enter your intranet login** (this is very important, the configurations are generated from it). The **Evaluation** tab generates a random configuration, similar to what is used during defense.

### Solving a level

- Edit the unshaded fields of the diagram until the network is correct.
- Click **[Check again]** to verify your configuration. The logs at the bottom of the page explain why a configuration is incorrect.
- When a level is solved, a **[Next level]** button appears.

### Exporting configurations

- Before moving to the next level, click **[Get my config]** to download the configuration of the current level.
- Repeat for each of the 10 levels.

### Submission details

- There are 10 levels, so **10 exported configuration files (one per level) must be placed at the root of the Git repository**, alongside this `README.md`.
- Double-check the file names before pushing.
- Only the content of the Git repository is evaluated during the defense.
- During the defense, you will have to successfully complete **three random levels** within a limited amount of time, without external tools (a simple calculator such as `bc` is tolerated, but it is the limit).

## Resources

### Networking concepts studied

- **TCP/IP addressing**: IPv4 addresses, network and host parts, private address ranges, network/broadcast addresses.
- **Subnet masks**: dotted decimal notation, CIDR notation (`/24`, `/30`, ...), computing the number of usable hosts, subnetting.
- **Default gateways**: the router interface used by a host to reach other networks.
- **Routers and switches**: routers forward packets between different networks using routing tables; switches connect devices within the same network.
- **Routing tables**: destination/mask, next hop, default route.
- **OSI layers**: the 7-layer model (physical, data link, network, transport, session, presentation, application), with a focus on layer 2 (switching) and layer 3 (IP routing).

### References

- [Wikipedia – Subnetwork](https://en.wikipedia.org/wiki/Subnetwork)
- [Wikipedia – Default gateway](https://en.wikipedia.org/wiki/Default_gateway)
- [Subnet Mask Cheat Sheet](https://www.aelius.com/njh/subnet_sheet.html)

### Use of AI

AI (Claude) was used **only once, to draft this `README.md`**: its structure and wording, based on the requirements of the project subject.

It was **not** used to solve any of the 10 levels or to produce any of the exported configuration files. The levels were solved by myself in the training interface.
