## Filestore NFS  Mount Options
0. Create a filestore instance following the instructions [here](https://cloud.google.com/filestore/docs/creating-instances)
1. Enable CSI Drivers on GKE Cluster
2. Deploy sc,pv,pod-pvc.yaml
3. Check content of mounted volume ```kubectl exec web-server -- ls /usr/share/nginx/html```
4. To get the node name for the pod```kubectl get pod web-server -o wide``` and copy the node name 
5. Connect ssh into GKE node ```gcloud compute ssh --zone "<zone-name>" "<node-name>" --tunnel-through-iap --project "<project-name>"```
6. Run ``` mount | grep nconnect=2``` and verify mount options
