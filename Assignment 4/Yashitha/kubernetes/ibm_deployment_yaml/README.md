apiVersion: apps/v1
kind: Deployment
metadata:
  name: flask-deploy

spec:
  replicas: 3
  selector:
    matchLabels:
      app: flask-deploy
  template:
    metadata:
      labels:
        app: flask-deploy

    spec:
      containers:
        - name: web
          image: jp.icr.io/website/web
          imagePullPolicy: Always
          ports:
            - containerPort: 5000
              protocol: TCP

