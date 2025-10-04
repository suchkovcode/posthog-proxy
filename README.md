# PostHog Reverse Proxy

https://posthog.com/docs/advanced/proxy

A reverse proxy allows you to send events to PostHog Cloud using your own domain.

This means that events are less likely to be intercepted by tracking blockers. You'll be able to capture more usage data without having to self-host PostHog.

Setting up a reverse proxy means setting up a service to redirect requests from a subdomain you choose (like e.yourdomain.com) to PostHog. It is best practice to use a subdomain that does not include posthog, analytics, tracking, or other similar words. 

You then use this subdomain as your api_host in the initialization of PostHog instead of us.i.posthog.com or eu.i.posthog.com.

```
posthog.init('phc_YOUR_TOKEN', {
  api_host: 'https://$SERVER_NAME'
})
```

## Getting Started

### One-click launch options

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/qHvw-4?referralCode=F6ei8i)

### Running

Requires both SERVER_NAME and PORT environment variables to be set. SERVER_NAME is the DNS address of this service, PORT is the port that the server will listen to, we recommend 80.

This does not use TLS, as it's assumed it will run on railway, which enforces TLS at it's edge proxy.

Dockerfile will populate nginx.conf template with the environment variables

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.
