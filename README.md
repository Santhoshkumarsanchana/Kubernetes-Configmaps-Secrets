# Kubernetes ConfigMaps & Secrets

Hands-on project on managing application configuration with ConfigMaps and Secrets.

## Approach

1. **Environment variable:** the ConfigMap value was injected with `valueFrom.configMapKeyRef` (`deployment-env.yml`). It is read once, when the container starts.
2. **Volume mount:** the ConfigMap was then mounted as a volume (`deployment-volume.yml`), exposing `db-port` as the file `/opt/db-port`. Updating the ConfigMap changed the file's content without rebuilding the image.

## 1. Troubleshooting ImagePullBackOff
![Troubleshooting](screenshots/01-troubleshooting.png)

## 2. Applying the Deployment and Checking Pods
![Apply and pods](screenshots/02-apply-pods.png)

## 3. Verifying the Config Value Inside the Pod
![Mounted value](screenshots/03-mounted-value.png)

## 4. Original Value (3306)
![Original value](screenshots/04-original-value.png)

## 5. Updating the ConfigMap (db-port: 3307)
![ConfigMap YAML](screenshots/05-configmap-yaml.png)

## 6. Updated Value Reflected in the Pod
![Updated value](screenshots/06-updated-value.png)

## 7. Creating a Secret
![Create secret](screenshots/07-create-secret.png)

## 8. Describing the Secret (Value Hidden)
![Describe secret](screenshots/08-describe-secret.png)
