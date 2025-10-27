## **Definition**

- Amazon CloudFront is a Content Delivery Network (CDN) that securely delivers web content, APIs, videos, and applications with low latency and high transfer speeds.
- It caches content at edge locations worldwide, reducing the load on origin servers and improving user experience.

## **Global Edge Network**

- CloudFront has **over 600+ edge locations** across the globe.
- Uses **Points of Presence (PoPs)** to cache and serve content closer to users.

## **Content Caching & Acceleration**

- **Static Content Caching** – Stores images, CSS, JavaScript, and other static files for faster delivery.
- **Dynamic Content Acceleration** – Optimizes dynamic content by reducing network hops.
- **Origin Shield** – Provides an additional layer of caching to reduce load on the origin server.

## **Origin Integrations**

- CloudFront can pull content from multiple **origin servers**, such as:
    - **Amazon S3** (for static websites and media files).
    - **Elastic Load Balancer (ALB/NLB)** (for dynamic applications).
    - **AWS Media Services** (for video streaming).
    - **On-Premise or Custom Origins** (for hybrid setups).

## **Performance Optimization**

- **HTTP/2 and HTTP/3 Support** – Reduces latency and speeds up page load times.
- **Edge Compute with Lambda@Edge & CloudFront Functions** – Runs serverless functions closer to users.

## **Security & Access Control**

- **AWS Shield & AWS WAF Integration** – Protects against DDoS attacks and malicious traffic.
- **Signed URLs & Signed Cookies** – Restricts access to authorized users only.
- **HTTPS & TLS Encryption** – Ensures secure content delivery.
- **Geo-Restriction** – Allows or blocks access based on geographic locations.
