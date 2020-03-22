# EKS

EKS 관련 Article 을 정리 해서 모아 놓았고, 나중에 다시 읽어 볼 목적이 제일 크다.

도입 해보고 싶은 Article 들도 있으니, 도입 후에는 후기 정도는 간단하게 작성하거나 별도의 문서를 작성해 볼 생각이다.

## Setup

### [AWS 서비스를 활용한 Kubernetes 클러스터 구축](http://engineering.vcnc.co.kr/2019/03/kubernetes-on-aws/)

* 아, EKS 처음 설치 시에 많은 도움이 되었던 글이다.

* k8s networking 에 대한 개념이 덜 잡혔을 때 보면서 좀 감이 오게 되었다.

* 그리고 eks 를 구성하면서 고민했던 포인트 들에 대해서도 많이 공감이 되었고 직접 eks 를 설치할때 기준 내지는 확장 해서 생각할 수 있게 해준 글이다

* eks 를 다시 처음 설치해야 하는 상황이 온다면 다시 한번 정독할 필요가 있음

### [IAM Roles for Service Accounts Technical Overview](https://docs.aws.amazon.com/eks/latest/userguide/iam-roles-for-service-accounts-technical-overview.html)

* aws 공식 document : [클러스터에서 서비스 계정의 IAM 역할 활성화](https://docs.aws.amazon.com/ko_kr/eks/latest/userguide/enable-iam-roles-for-service-accounts.html)

* Service Account 에 IAM Roles 을 부여해서 S3 등 AWS resource 에 접근 가능한 방법에 대해 설명해주고 있다

* 정독하진 못했지만, 반드시 쓰임새가 있을 것이므로 keep

* worker node 에 IAM role 을 부여하면 모든 pod 에 동일한 IAM role 을 갖게 되므로 위험하고,

* pod 별로 role 을 부여할 수 도 있지만, service account 에 IAM role 을 부여하면 훨씬 유연하게 사용 가능할거라 생각됨

* 하지만 써봐야 감이 올 듯, 어느 부분에서 한계를 발견할 수도,,,,

### [Amazon EKS, Kubernetes 클러스터 퍼블릭 엔드포인트에 대한 네트워크 액세스 제한 활성화](https://aws.amazon.com/ko/about-aws/whats-new/2019/12/amazon-eks-enables-network-access-restrictions-to-kubernetes-cluster-public-endpoints/)

* EKS Master node api 가 public 오픈 되어서 이래저래 보안에 말이 많았는데, cidr 기반으로 액세스를 제어 가능하게끔 됨

* 자세한건 설명서에서 확인 가능함. [Amazon EKS Cluster Endpoint Access Control](https://docs.aws.amazon.com/eks/latest/userguide/cluster-endpoint.html)

* 실제로 적용 해보면서 다시 정독 필요

### [관리형 노드 그룹](https://docs.aws.amazon.com/ko_kr/eks/latest/userguide/managed-node-groups.html)

* EKS Kubernetes 1.14 version 부터는 worker node 도 관리형으로 변경되는거 같은데 어느 정도까지 지원해 주는지 확인 필요할듯 싶다

* 관련 aws 영문 블로그 [Extending the EKS API: Managed Node Groups](https://aws.amazon.com/ko/blogs/containers/eks-managed-node-groups/)

### [Amazon EBS CSI 드라이버](https://docs.aws.amazon.com/ko_kr/eks/latest/userguide/ebs-csi.html)

* ebs volume 을 관리 해주기 위한 별도의 플러그인(?)을 설치해주는 듯한 느낌인데, 이것도 직접 해봐야 느낌이 올수 싶다

* 당장은 아직 필요성을 느끼지 못하고 있긴하다.

* [Amazon Elastic Block Store (EBS) CSI driver](https://github.com/kubernetes-sigs/aws-ebs-csi-driver) 에서 보면 지원하는 기능이,,

  ```text
  Static Provisioning - create a new or migrating existing EBS volumes, then create persistence volume (PV) from the EBS volume and consume the PV from container using persistence volume claim (PVC).
  Dynamic Provisioning - uses persistence volume claim (PVC) to request the Kuberenetes to create the EBS volume on behalf of user and consumes the volume from inside container. Storage class's allowedTopologies could be used to restrict which AZ the volume should be provisioned in. The topology key should be topology.ebs.csi.aws.com/zone.
  Mount Option - mount options could be specified in persistence volume (PV) to define how the volume should be mounted.
  NVMe - consume NVMe EBS volume from EC2 Nitro instance.
  Block Volume (beta since 1.14) - consumes the EBS volume as a raw block device for latency sensitive application eg. MySql
  Volume Snapshot (alpha) - creating volume snapshots and restore volume from snapshot.
  Volume Resizing (alpha) - expand the volume size.
  ```

  보면 쓸만한 기능이 보인다.

### [EKS Getting Started Guide Configuration](https://github.com/terraform-providers/terraform-provider-aws/tree/master/examples/eks-getting-started)

* eks 를 Terraform 으로 구성할때, Tutorial 이 있으면 확실히 이해도도 빨리 오르고, 확장해서 요구사항에 맞게 다시 구성하는것도 훨씬 편하다

* 한번 본 후에는 그닥 보지 않을 가능성이 큼..

* terraform eks module : [terraform-aws-eks](https://github.com/terraform-aws-modules/terraform-aws-eks)

* terraform eks module 은 언제라도 새로 구성할때는 가져다 쓰게 되어 있다.

* 아마 축소해서 원하는 수준으로 다시 가공 하겠지만,,

## Security

### [Guide to Designing EKS Clusters for Better Security](https://www.stackrox.com/post/2020/03/guide-to-eks-cluster-design-for-better-security/)

* 이것도 거의 흡사한 Article : [Amazon EKS Security Best Practices](https://www.stackrox.com/post/2019/09/amazon-eks-security-best-practices/?utm_sq=gbia7mryla)

* EKS 구성 시 Security 를 처음에는 간과하게 되지만 반드시 신경 써서 봐야할 부분이므로, 추후에 반드시 체크 필요
