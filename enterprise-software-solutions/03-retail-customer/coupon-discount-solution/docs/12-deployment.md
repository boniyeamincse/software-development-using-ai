# 12 - Coupon Deployment Strategy

## Speed-First Deployment
- **Global Edge Deployment**: Deploying the evaluation logic to edge nodes (e.g., AWS Lambda@Edge) to ensure the cart total updates instantly for users worldwide.
- **Warm Replicas**: Maintaining multiple active Redis nodes to prevent "Cold Start" lag on budget verification.

## Monitoring
- **Error-Rate Monitoring**: Alerting if the `/evaluate` endpoint latency exceeds 50ms.
- **Economic Safety Checks**: Automated background job that compares "Projected Discount Cost" vs "Actual DB Redemption Sum" every hour.

## Stress Testing
- **Black Friday Simulations**: Testing the engine's ability to handle 10,000 evaluations per second with 50,000 active rules in the cache.
