[![GoKEV](http://GoKEV.com/GoKEV200.png)](http://GoKEV.com/)

<div style="position: absolute; top: 40px; left: 200px;">

# GoKEV ansible-dns-change
</div>

This has been tested in EL5, EL6, EL7, Ubuntu 16, Windows 10, Windows 2016

## To change DNS on an EL6, EL7, Windows machine:

  1. Modify the list of NS addresses you wish to use in `defaults/main.yml` or pass a list of servers as the variable `resolv_nameservers`.  
      - **Note**: This will be a list, as such: 
<pre>resolv_nameservers:
  - 8.8.8.8
  - 8.8.4.4
  - 75.75.75.75  </pre>


- 2. Launch the role against your inventories via `site.yml`.

Make sure your Windows authentication is configured correctly at the group level.


## To change DNS on an EL5 machine (and possibly anything without compatible python):
  1. Modify the list of NS addresses you wish to use in `site_nopython.yml` or pass the text of a new `/etc/resolv.conf`.  This will be content piped into the variable called `resolv_text` as so:
<pre>- resolv_text: |
nameserver 8.8.8.8
nameserver 8.8.4.4
nameserver 75.75.75.75</pre>

  2. Launch with the `site_nopython.yml`.  This is tested and working in CentOS5 and RHEL5.



## Troubleshooting & Improvements

- Not enough testing yet

## Notes

  - Not enough testing yet

## Author

This project was created in 2018 by [Kevin Holmes](http://GoKEV.com/).


