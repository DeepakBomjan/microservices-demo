## Create a service account & assign the policy
```bash
gcloud config set project playground-s-11-900c0e54
gcloud iam service-accounts create gke-test
gcloud projects add-iam-policy-binding playground-s-11-900c0e54 --member="serviceAccount:gke-test@playground-s-11-900c0e54.iam.gserviceaccount.com" --role="roles/owner"


```
## Create a credential key for the service account
```bash
gcloud iam service-accounts keys create cred.json --iam-account=gke-test@playground-s-11-900c0e54.iam.gserviceaccount.com

```

##  Set environment variable for credential key

```bash
export GOOGLE_APPLICATION_CREDENTIALS="./cred.json"
```

## Enable APIs

```bash
gcloud services enable container.googleapis.com
gcloud services enable cloudresourcemanager.googleapis.com

```
