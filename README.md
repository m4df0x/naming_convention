# naming_convention
Naming convention for objects on a firewall (FortiGate)
# Firewall-objects
## Hosts IPv4
    hst_[IP]
    example: hst_10.1.1.1
## Hosts IPv6
    hst6_[IP]
    example: hst6_0:0:0:0:0:0:0:0

## Netze IPv4
    net_[network]_[netmask]
    example: net_10.0.0.0_16

## Netze IPv6
    net6_[network]_[netmask]
    example: net6_0:0:0:0:0:0:0:0_128

## Netzbereiche
    rng_[start-IP]-[end-IP]
    example: rng_10.12.70.20-10.12.70.29

## Geolocation
    geo_[countryname]
    example: geo_china, geo_russia

## FQDN
    fqdn_[name]
    example: fqdn_example.com

## Hostgruppen
    grp_hst_[zone/function]
    example: grp_hst_ad, grp_hst_syslog

## Netzgruppen
    grp_net_[zone/function]
    example: grp_net_clients, grp_net_printer

# Ports and Services
## Ports
    [protocol]_[portnumber]_[*ht*] (ht for High Timeout)
    example: tcp_3306, udp_3306, tcp_3306_ht tcp_udp_3389
    
## Portranges
    [protocol]_[start-port]-[end-port]
    example: tcp_5000-5900, udp_5000-5900

## Servicegruppen
    grp_srv_[direction]_[function]
    example: grp_srv_to_wsus, grp_srv_from_wsus

## Usergruppen
    grp_usr_[Abteilung/Funktion]
    example: grp_usr_marketing, grp_usr_verkauf, grp_usr_webadmin

## VirtualIPs
    vip_[externalIP]
    examplee: vip_80.80.80.80
    
## VirtualIP-Group
    grp_vip_[Funktion]
    example: grp_vip_VPN-Gateways (Gruppe beinhaltet dann einzelne vip's)

# Templates
## Templates
    tpl_[Funktion]_[Location]
        example: tpl_sdwan_center, tpl_ipsec_branch, tpl_system_all

## Templategruppen
    grp_tpl_[type]_[Location]
    *type* = CLI,VPN,System,SDWAN
    example: grp_tpl_vpn_center, grp_tpl_system_branches, grp_tpl_sdwan_branch-china

# Security-profiles
    av	    Antivirus
    ac	    ApplicationControl
    ips	    IntrusionPrevention
    dns	    DNS Filter
    wf	    WebFilter
    ff	    FileFilter
    vf	    VideoFilter
    ssl     SSL/SSH Inspection

## flowtype
    pb	    Proxy-Based
    fb	    Flow-Based
## handling/action
    monitor/block/allow

## profile group
    pg profile group

## example
  av_pb_default
  ips_pb_windows-server
  wf_fb_linux-updates
  ssl_no-inspection

# VPNs
## phase1-interface
    vpn_p1_<src>-<dst>_<info> [max. length 15 Characters]
        src	Source IP/name/abbrivation
        dst	Source IP/name/abbrivation
        info	MPLS/DSL/DAILUP or Number
## phase2-interface
    vpn_p2_[localnet]-[remotenet]_<info> [max. length 15 Characters]
        src	Source IP/name/abbrivation
        dst	Source IP/name/abbrivation
        info	MPLS/DSL/DAILUP or Number

# SDWAN
    sdwanzone_[name]      SDWAN-Zone
    example: sdwanzone_wan, sdwanzone_hub, sdwanzone_sase

psla_    performance sla
sd_rule
