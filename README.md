# Jenkins Kubernetes Kurulumu (Türkçe)


# Jenkins Kubernetes Kurulumu

Bu depo, Kubernetes üzerinde Jenkins'i kurmak için gerekli yapılandırma dosyalarını içerir. Dosyalar şunları içerir:

- `jenkins-deployment.yaml`: Jenkins Deployment tanımı.
- `jenkins-service.yaml`: Jenkins Service tanımı.
- `jenkins-pvc.yaml`: Jenkins için Persistent Volume Claim (PVC).
- `jenkins-ingress.yaml`: Jenkins'e erişim için Ingress tanımı.

## Kurulum Adımları

1. Öncelikle, bir StorageClass oluşturun. Bu, PVC'nin depolama alanını sağlayacaktır.
2. Yukarıda listelenen YAML dosyalarını sırasıyla uygulayın:
   ```
   kubectl apply -f jenkins-pvc.yml
   kubectl apply -f jenkins-deployment.yaml
   kubectl apply -f jenkins-service.yaml
   kubectl apply -f jenkins-ingress.yaml
   ```
3. Jenkins servisine erişmek için, Ingress tanımında belirtilen host adını kullanın.

## Notlar

- Bu yapılandırma, örnek bir Jenkins kurulumunu temel alır. Özelleştirmeler için dosyaları kendi ihtiyaçlarınıza göre düzenleyin.
- StorageClass ve Ingress yapılandırmanız kubernetes ortamınıza göre değişiklik gösterebilir.

# Jenkins Kubernetes Setup (English)


# Jenkins Kubernetes Setup

This repository contains the necessary configuration files for setting up Jenkins on Kubernetes. The files include:

- `jenkins-deployment.yaml`: Jenkins Deployment definition.
- `jenkins-service.yaml`: Jenkins Service definition.
- `jenkins-pvc.yaml`: Persistent Volume Claim (PVC) for Jenkins.
- `jenkins-ingress.yaml`: Ingress definition for accessing Jenkins.

## Setup Instructions

1. First, create a StorageClass. This will provide the storage for the PVC.
2. Apply the YAML files listed above in order:
   ```
   kubectl apply -f jenkins-pvc.yml
   kubectl apply -f jenkins-deployment.yaml
   kubectl apply -f jenkins-service.yaml
   kubectl apply -f jenkins-ingress.yaml
   ```
3. To access the Jenkins service, use the host name specified in the Ingress definition.

## Notes

- This configuration is based on a sample Jenkins setup. Customize the files according to your needs.
- Your StorageClass and Ingress configuration may vary depending on your Kubernetes environment.
