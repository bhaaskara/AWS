# Route 53
Amazon Route 53 is a highly available and scalable cloud [Domain Name System (DNS)](https://aws.amazon.com/route53/what-is-dns/) web service.

## Types of routing policies
1. simple routing policy
    Used for single resource that performs a given function for your domain. Like the webserver that serves content for your wesite.
2. Failover routing policy
    This policy comes into use when you want to configure active-passive failover. Failover occurs when system automatically transfers control to other system.
3. Geo location routing policy
    Geo location routing policy is used when you want to route traffic based on the location of the users.
4. Geo proximity policy
5. Latency routing policy
    use this policy when you have resources in multiple  AWS regions and you want to route  traffic to the region that provides less latency. 

```
simple routing
weighted
geolocation
latency
failover
multivalue
```