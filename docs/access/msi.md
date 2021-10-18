# *The Minnsota Supercomputing Institute (MSI) provides the software, hardware, storage and experts to support research projects in all reserach areas.*

## **Registering for Access**

### *UMN Employees*

[Request an MSI account](https://www.msi.umn.edu/access) and your account can be created from your UMN InternetID (formerly called x500).

### *Non-UMN Employees*

In order to request an MSI account as a non-UMN employee, a Person of Interest (POI) account must first be created. The requestor needs written approval from Dr. Damien Fair or another DCAN Leadership team member. Send written approval to Nora Byington (bying015@umn.edu) to initiate the POI account creation process.

## **Gaining Access**

1. To remotely log into MSI you need to establish a VPN connection. Detailed instructions can be found on [HST/AHC: VPN and Remote Desktop Setup](https://it.umn.edu/services-technologies/how-tos/hstahc-vpn-remote-desktop-setup).

    NOTE: if you already have VPN on your computer for another institution, you will need to complete the following steps:

    - type "tc-vpn-1.umn.edu" in the box
    - choose "anyconnect-UofMvpnfull" from the group
    - enter username and password

      *This installs required setups for VPN, after which you will have a dropdown with UMN choices and can use split tunnel moving forward.*

      *If you receive an error message the first time, simply re-open Cisco.*

2. Structure of High Performance Computer (HPC) Systems  

   - To learn more about the structure of the HPC system, visit the [MSI website](https://www.msi.umn.edu/tutorials) for a list of tutorials.  
   - **Launch a Terminal** - To Launch a terminal, visit [NX](https://nx.msi.umn.edu/nxwebplayer) or [NICE](https://nice.msi.umn.edu) and login with your UMN credentials.  
   - **Enter Mesabi Node** - To access files and request resources for a job, you must log into the Mesabi Node.  

      - `ssh -Y miran045@mesabi.msi.umn.edu`
      - replace `miran045` with your username

   - Request resources for interactive computing. **As default, you should request an interactive node**. In some cases (i.e. high priority projects) you might request access to the **dcan** node

      a. **Default** | [mesabi](https://www.msi.umn.edu/content/mesabi) resources
        - `srun -N 1 --ntasks-per-node=4  --mem-per-cpu=4gb -t 4:00:00 -p interactive --x11 --pty bash`
        - (update time and memory as needed).
            - To change memory, change the argument of the flag `--mem-per-cpu`
            - To change time, change the argument of the flag `-t`

      b. **Using the dcan node**. Reserve this node for high priority/high RAM/CPU power demands
        - `srun -N 1 --cpus-per-task=4 --mem-per-cpu=4gb -t 4:00:00 --x11 -p dcan --pty bash`
        - (update time and memory as needed).
            - To change memory, change the argument of the flag `--mem-per-cpu`
            - To change time, change the argument of the flag `-t`

   - [Load the module you need](https://www.msi.umn.edu/support/faq/what-module). For example, if you want to run matlab, just type in terminal `module load matlab`

### Additional details

For non-interactive jobs, use [slurm](https://www.msi.umn.edu/content/job-submission-and-scheduling-slurm) for job submissions. This [link](https://www.msi.umn.edu/partitions) points to a table that shows the memory and time capacity of each partition for non-interactive jobs.

If you experience delays or problems accesing the MSI or a particular node, the reason could be that the MSI might be non-fully operational at that time. The first Wednesday of each month the system is down for maintenance. Use the following links to check the MSI system and node status at any time:

- [MSI System status](https://status.msi.umn.edu/)
- [MSI node status](https://umgcdownload.msi.umn.edu/website/slurmnodes/index.html)

## *Reporting Errors*

If you are experiencing errors/issues, contact the following people:

- Parallelization or code running issues: Tim Hendrickson (hendr522@umn.edu)

- General usage or slumn issues: MSI help desk (help@msi.umn.edu)

- Pipeline issues:

  - Infant pipeline: Kathy Snider (sniderk@ohsu.edu)
  
  - Human pipeline: Anders Perrone (perronea@ohsu.edu)

  - Macaque pipeline: Thomas Madison (madisoth@ohsu.edu)

  - Rodent pipeline: Thomas Madison (madisoth@ohsu.edu)
  