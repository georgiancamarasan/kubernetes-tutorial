## Working with object files

* `kubectl apply -f obj.yaml` - Update the kubernetes cluster with the objects from the file.
* `kubectl apply -f obj.yaml --dry-run` - Print the objects to the terminal without sending them to the server.
* `kubectl apply -f obj.yaml --view-last-applied` - Show the last state applied to the object.
* `kubectl delete -f obj.yaml` - Delete the objects from the file. It will not prompt to confirm.

## Object file
    apiVersion: v1
    kind: Pod
    metadata:
      name: "kuard"
      namespace: default
      labels:
        app: "kuard"
    volumes:
      - name: "kuard-data"
        hostPath:
          path: "/var/lib/kuard"l
    spec:
      containers:
      - name: kuard
        image: "georgiancamarasan/kuard:blue"
        volumeMounts:
          - mountPath: "/data"
            name: "kuard-data"
        resources:
          requests:
            cpu: 500m
            memory: 128Mi
          limits:
            cpu: 1000m
            memory: 256Mi
        livenessProbe:
          httpGet:
            path: /healthy
            port: 8080
          initialDelaySeconds: 5
          timeoutSeconds: 1
          periodSeconds: 10
          failureThreshold: 3
        ports:
        - containerPort: 8080
          name:  http
          protocol: TCP
    ---
