<p align="center">
<img src="https://i.imgur.com/CtGfsq8.png" alt="osTicket logo"/>
</p>

<h1>Building Intuition for DNS</h1>
In this tutorial, we will build a solid fundamental understanding of DNS. We will be experimenting with DNS A-Records on a server, creating and deleting records. Additionally, we will explore concepts such as CNAME records and Root hints.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Command Line
- Microsoft Active Directory

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

<h2>List of Prerequisites</h2>

- Active Directory Virtual Machine
- Client Machine joined to your domain
- Microsoft Azure with two pre-configured VMs: Client-1 and DC-1
- Microsoft Active Directory installed on DC-1 and promoted to a domain controller

<h2>Video Demonstration</h2>
To further enhance your understanding of DNS concepts and the exercises we will be performing, we have prepared a video demonstration for you. This video will provide a visual walkthrough of the steps involved in building intuition with DNS.

### [Building Intuition with DNS](https://drive.google.com/file/d/1hh8iskP98lgcyR_fRVLUTXlAIvu7UoWn/view?usp=drive_link)


Now, let's dive into the lab exercises and explore DNS A-Records, DNS caching, and CNAME records.

<h2>Lab Steps</h2>

**A-Record Exercise**

First, we will inspect DNS A-Records on the server. A-Records are hostname to IP address mappings. Follow these steps:

1. Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin).
2. Connect/log into Client-1 as an admin (mydomain\jane_admin).
3. From Client-1, try to ping "mainframe." Notice that it fails.
4. Nslookup "mainframe" and notice that it fails (no DNS record).
5. Create a DNS A-record on DC-1 for "mainframe" and have it point to DC-1's private IP address.
6. Go back to Client-1 and try to ping "mainframe." Observe that it works.

**Local DNS Cache Exercise**

1. Go back to DC-1 and change the record address of "mainframe" to 8.8.8.8.
2. Go back to Client-1 and ping "mainframe" again. Observe that it still pings the old address.
3. Observe the local DNS cache using the command `ipconfig /displaydns`.
4. Flush the DNS cache using the command `ipconfig /flushdns`. Observe that the cache is empty.
5. Attempt to ping "mainframe" again. Observe that the address of the new record is now showing.

**CNAME Record Exercise**

1. Go back to DC-1 and create a CNAME record that points the host "search" to "www.google.com."
2. Go back to Client-1 and attempt to ping "search." Observe the results of the CNAME record.
3. On Client-1, use `nslookup` to query "search" and observe the results of the CNAME record.

By following these steps, you will gain a better understanding of DNS, A-Records, DNS caching, and CNAME records.
