# DNS

- DNS (Domain Name System) is a system that translates domain names to IP addresses.
- DNS in node us to resolve domain names to IP addresses.

## dns.lookup()

- The `dns.lookup()` method is used to resolve a domain name (e.g. 'google.com') into an IP address.
- The method takes the following parameters:
  - `hostname`: The domain name to resolve.
  - `options`: An object that can have the following properties:
    - `family`: The IP family (4 or 6).
    - `hints`: The flags that are passed to the underlying `getaddrinfo()` system call.
    - `all`: If `true`, the method returns an array of all resolved addresses.
  - `callback`: A callback function that is called with the resolved address.

```javascript
// Import the DNS module from Node.js standard library
const dns = require("dns");

/**
* Factory function that returns a callback handler for DNS lookups
* This approach allows reusing the same callback logic for different lookups
* @returns {Function} Standardized callback function for DNS lookup operations
*/
const lookupCallback = () => (err, address, family) => {
    if (err) {
        console.error(`Lookup Error:`, err);
        return;
    }
    // Format the output with clear indication of IP version and address
    console.log(`${family === 4 ? 'IPv4' : 'IPv6'} Address: ${address}`);
};

// Basic DNS lookup for localhost with default options
// This will return either IPv4 or IPv6 depending on system configuration
dns.lookup('localhost', lookupCallback());

// IPv4-specific lookup for localhost
// The family:4 option forces the lookup to return only IPv4 addresses
dns.lookup('localhost', { family: 4 }, lookupCallback());

// Resolve all record types for google.com
dns.resolveAny("google.com", (err, addresses) => {
    if (err) {
        console.error("Lookup error:", err);
        return;
    }
    console.log("Addresses for google.com");
    // Extract IPv4 address from A records
    const ipv4 = addresses.find((addr) => addr.type === "A")?.address;
    // Extract IPv6 address from AAAA records
    const ipv6 = addresses.find((addr) => addr.type === "AAAA")?.address;

    // Display results with fallback text if addresses aren't found
    console.log(`IPv4 Address: ${ipv4 || "Not found"}`);
    console.log(`IPv6 Address: ${ipv6 || "Not found"}`);
});

// Comprehensive IP lookup for localhost retrieving all address families
dns.lookup("localhost", { all: true }, (err, addresses) => {
    if (err) {
        console.error("Lookup error:", err);
        return;
    }
    console.log("Address for localhost");
    // Find and extract the IPv4 address from the results array
    const ipv4 = addresses.find((addr) => addr.family === 4)?.address;
    // Find and extract the IPv6 address from the results array
    const ipv6 = addresses.find((addr) => addr.family === 6)?.address;

    // Display both address types with appropriate fallback messages
    console.log(`IPv4 Address: ${ipv4 || "Not found"}`);
    console.log(`IPv6 Address: ${ipv6 || "Not found"}`);
});
```
