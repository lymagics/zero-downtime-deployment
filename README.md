# Zero Downtime Deployment
**Zero Downtime Deployment** is an approach of releasing software that guarantees that a service or application will not go offline at any point throughout the rollout process.

### Flow
1. Run instances:
```
docker-compose up -d
```
2. Stop green instance:
```
docker-compose stop green
```
3. Go to your browser and check http://localhost:8080/ping still working.
4. Make changes app.py file (add new endpoint or change existing).
5. Start green instance:
```
docker-compose up --no-deps -d --build green
```
6. Go to your browser and check http://localhost:8080/ping multiple times. Some of requests will be proxies to green instance with your updates.
7. Repeat steps 2-6 thing for blue instance.
8. Now your app new features deployed without going offline. 