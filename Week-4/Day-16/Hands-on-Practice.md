### Hands-On Practice

**Practice Exercises:**

1. Check listening ports: ss -tlnp
2. Trace route to Google: traceroute -n google.com
3. Query DNS: dig github.com +short
4. Find who’s using port 22: ss -tlnp | grep :22
5. Check socket summary: ss -s

### Interview Question

Q: How would you troubleshoot network connectivity issues?

A: I use a systematic approach:

1. Check if service is listening: ss -tlnp
2. Verify DNS resolution: dig domain.com +short
3. Trace network path: traceroute destination
4. Check active connections: ss -ta
   
This identifies if the issue is DNS, routing, or service-related.
