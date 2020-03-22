# AWS

## Useful Link

### [aws workshop link](https://www.sagemaker-workshop-kr.com/kr/references.html?fbclid=IwAR3OkaGAKKQhlLXKgYybZxsT9_vJqh9mG5a-E5U7-w3f0jx7R5XW9NRCmh4)

* ml, container, iac 등 각종 workshop 링크들이 모여 있어서 한눈에 파악이 가능하다.

* 관련 workshop 자료 따로 따로 되어 있어서 찾아보기가 의외로 쉽지 않은데 한군데 정리되어 있어서 좋다.

## 비용

### [EC2 비용 뒤집어 보기](https://wisen.co.kr/pages/blog/blog-detail.html?idx=4329)

* 사실 주요 비용만 확인하고 실제로 세세한 비용은 잘 안보게 되는데 그런 비용들에 대해 세세하고도 간단하고 쉽제 설명해 놓은 글이다.

* 비용 볼때 한번씩 꺼내서 같이 보면 훨씬 도움 이 된다. aws 비용에 대해 이해하는데에 말이다

### [AWS Cloud Cost Checklist V2](https://www.sensedeep.com/blog/posts/stories/checklist-to-lower-aws-cloud-costs.html)

* 아직 자세히는 안봤지만, 비용 관련해서 정리할 때 이 체크리스트 기준으로 정리하면 좋을 듯 싶다

### [AWS EBS(Elastic Block Storage) 비용 최적화](https://ericygkim.wordpress.com/2019/07/11/aws-ebselastic-block-storage-%EC%9D%98-%EB%B9%84%EC%9A%A9-%EC%B5%9C%EC%A0%81%ED%99%94/)

* aws ebs 비용에 대해 꽤나 딥하게 설명 해놓은 글이다.

* ebs 비용에 대해 좀 딥하게 살펴볼 때 같이 보면 좋을듯 싶다.

## Security

### [How to get specific security information about AWS services](How to get specific security information about AWS services)

* aws service 에 대한 security document 링크를 모아 둔 글이다.

* aws 공식 document 도 가끔 특정 주제를 찾아 들어가기 힘든 경우도 있는데, security 같은 민감한 주제에 대해 한번에 접근할 수 있는 링크들은 유용할 듯 싶다.

### [AWS에서 네트워크 공격 자동차단 하기](https://woowabros.github.io/security/2018/02/23/aws-auto-security1.html)

* 우형에서 aws 네트워크 보안에 대한 글이다. 아직 이런 분야 까지는 실제로 해본적이 없지만,

* 언젠가는 반드시 진행해야 될 내용이므로, 실제로 구성할때 많은 도움이 될듯하다.

### [AWS 보안 서비스의 기능 제대로 활용하기](https://aws.amazon.com/ko/blogs/korea/aws-heroes-putting-aws-security-services-to-work-for-you/)

* aws 보안 서비스에 대한 공식 블로그 글이다.

* security 는 해야지 하면서 아직 진지하게 진행 안해봐서 이런 글들을 통해서 상황이 됐을때, 진행 해봐야 한다.

### [AWS 보안 모범 사례 백서 (번역/요약)](https://futurecreator.github.io/2018/07/13/aws-security-best-practies/)

* aws 보안 모범 사례 백서를 요약 해놓은 글이다.

* 영어 문서는 아무래도 한글 문서 보다 읽는데 시간이 더 들다 보니, 이런글은 참 주옥 같다.

* 번역까지 해주신 분에게 감사하는 마음으로 잘 읽고 활용!

## Iam

### [Continuously monitor unused IAM roles with AWS Config](https://aws.amazon.com/ko/blogs/security/continuously-monitor-unused-iam-roles-aws-config/)

* 주기적으로 iam role 을 체크해서 사용하지 않거나 한 iam role 을 모니터링 하는 구성을 소개 해주는 글이다.

* iam role 이 terraform 으로 관리하더라도 나중에는 관리가 쉽지 않은데 이렇게 구성해 놓으면 어려모로 도움이 많이 될 듯 싶다.

### [AWS IAM best practices](https://www.joinc.co.kr/w/man/12/aws/iam_bf)

* aws iam best practies 공식 글은 아니다.

* 보통 이런 best practies 는 공식 글이 잘되어 있고, 업데이트도 잘되고 해서 공식 문서글을 보통 기준으로 삼고 읽는 편인데,

* 이번 글에 내용들은 공식 홈글과 같이 참고하면 좋을듯 싶다.

## Other

### [Best practices for tagging your infrastructure and applications](https://www.datadoghq.com/blog/tagging-best-practices/)

* aws 에 국한된 tagging 전략에 대한 내용은 아니지만, 사례들을 많이 들고 있어서 좋은 참고가 될거 같다

* k8s 등 infra 에서는 tag 로 정리하는게 필요한데 매번 그 기준이 애매해서 best practice 는 많이 도움이 될 듯 싶다

### [Application Load Balancing via IP Address to AWS & On-Premises Resources](https://aws.amazon.com/ko/blogs/aws/new-application-load-balancing-via-ip-address-to-aws-on-premises-resources/)

* 2017 년 글이긴 하지만, alb 에서 ip 기반으로 라우팅이 가능한지 몰랐었는데 이글 때문에 알게 되었다.

* 당장 도입할 일은 없긴 하지만, 추후 infra 설계 시 좀더 확장 되게 생각할 수 있게 되었다.

* 원래는 direct connect 로 연결된 idc 의 서버를 이렇게 구성해 볼까 생각했었는데, direct connect 도 연결 안된 상태여서 생각만 해본정도라 추후 상황이 되면 검증해보면 좋을 듯 싶다.

### [Multi-Cloud Architectures for the Enterprise](https://medium.com/swlh/multi-cloud-architectures-for-the-enterprise-part-1-623530b6b4c4)

* multi cloud architecture 에 대한 글이다. 아직 multi cloud 까지는 생각 전이라 일단 keep 만.

### [Amazon Connect를 이용한 장애 대응도구 개발기](https://www.slideshare.net/awskr/amazon-connect-222841497)

* amazon connect 로 outbound call 을 어떻게 구성 했는지에 대한 글이다.

* 이렇게 구성 가능하다라는것을 처음 알게되었다.

* 시간만 좀 있었으면 이렇게 구성해볼만한 상황도 있긴 했었는데,

* 흠 관련해서는 기회가 된다면 참고해서 구성해보면 좋을듯 싶다.

* 한국 리전에서는 안되는 등 몇가지 단점이 보이긴 함...

### 이미지 리사이징

* [AWS - serverless-image-handler](https://medium.com/@kevin_park/aws-serverless-image-handler-de68255bc879)
  * 이미지 리사이징 라이브러리가 많이 개선되어서 이미지를 미리 리사이징 해두지 않고 이미지 요청 시 리사이징 해서 반환 해주는 형태의 구성을 공유 해준 글이다.
  * 흠,, 괜찮을 수도 있겠다 싶다. 성능이랑 비용만 괜찮다면,,,

### [AWS SSM으로 EC2 인스턴스에 접근하기 (SSH 대체)](https://musma.github.io/2019/11/29/about-aws-ssm.html)

* 흠 기존 ssh 대신 ssm 으로 ec2 에 접속 하는 방법에 대해 설명 해준 글이다

* 어느면에서는 괜찮다고 생각 되어진다. iam 으로 제어 가능하니 훨씬 유연할거 같기도 하고,

* 거기다 private subnet 에 있는 ec2 직접 붙을 수 있으니 bastion 도 필요 없어지고,

* 추후 한번 해볼 필요가 있겠다.

### aws 공인 자격증

* [당근 마켓 - AWS 솔루션 아키텍트 어소시에이트 자격증 취득 후기](https://www.44bits.io/ko/post/aws-certification-solutions-architect-associate)

### [AWS-to-Slack](https://github.com/arabold/aws-to-slack)

* aws cloudwatch alarm 등을 구성할때 참고하거나 그냥 가져다 쓰면 좋을듯 싶다.

### [CloudWatch 메트릭 그래프 스냅샷 만들기](https://brunch.co.kr/@alden/53)

* aws cloudwatch graph 이미지를 lambda 함수로 가져와서 slack 으로 뿌려주는 구성을 설명한 글이다.

* boto3 library 를 사용해서 이미지를 만든좀이 특이하다.

* 전에 puppeteer 를 통해 kibana 그래피를 가져와서 slack 뿌려준 경험이 있는데 둘중 머가 나은지는 좀더 고민이 필요하겠지만, cloudwatch 한정 이라는 점에서 puppeteer 를 다시 사용할 가능성이 크긴 하다

### [Amazon RDS에서 민감한 데이터 보안을 위한 모범 사례](https://aws.amazon.com/ko/blogs/korea/applying-best-practices-for-securing-sensitive-data-in-amazon-rds/)

* 일반적인 모범사례지만, 최소한 여기 나오는 내용은 따라줘야 기본은 지킨다라는 의미 일거 같다.

* rds 를 생성시에는 여기 내용을 한번 씩 체크해봐야 한다.



