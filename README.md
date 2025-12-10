# observable
Tempo + Loki + Pyroscope + Alloy + prometheus



## Running the Demo

### Step 1: Clone the repository
```bash
git clone https://github.com/zhangsongyang/observable.git
```

### Step 2: Deploy the monitoring stack
```bash
docker-compose up -d
```

### Step 3: Access Grafana Alloy UI
Open your browser and go to `http://localhost:12345`.

### Step 4: Access Grafana UI
Open your browser and go to `http://localhost:3000`.

### Step 5: Run your Java application with OpenTelemetry and Pyroscope agents
```bash
java -javaagent:D:\code\github\observable\opentelemetry\opentelemetry-javaagent.jar \
-javaagent:D:\code\github\observable\opentelemetry\pyroscope.jar \
-Dpyroscope.application.name=anhui-carbon-server \
-Dpyroscope.server.address=http://localhost:9999 \
-Dotel.service.name=anhui-carbon-server \
-Dotel.exporter.otlp.endpoint=http://localhost:4318 \
-Dotel.exporter.otlp.protocol=http/protobuf \
-jar my-application.jar
```






