# 🌐 Smart Static Website

이 프로젝트는 정적 웹사이트를 AWS 인프라를 활용해 자동으로 배포하는 연습용 프로젝트입니다. GitHub를 소스 저장소로 사용하고, AWS CodePipeline을 통해 S3에 자동 배포되도록 구성되어 있습니다.

---

## 🧰 사용된 AWS 리소스

- **Amazon S3**: 정적 웹사이트 호스팅
- **CloudFront**: 전 세계에 빠르게 콘텐츠 전송
- **AWS Certificate Manager (ACM)**: HTTPS용 SSL 인증서 관리
- **AWS WAF**: 웹 방화벽 설정
- **CloudWatch**: 모니터링 및 로그 확인
- **CodePipeline**: CI/CD 자동 배포 파이프라인

---

## 🛠 구축 순서

1. **웹사이트 제작**
   - `index.html` 파일을 이용해 정적 웹사이트 제작

2. **GitHub 리포지토리 생성**
   - 소스 코드를 업로드하여 AWS에서 자동 배포할 수 있도록 준비

3. **AWS 리소스 세팅**
   - S3 버킷 생성 및 정적 웹 호스팅 설정
   - CloudFront 배포 생성 및 ACM 인증서 연결
   - WAF 설정으로 보안 강화
   - CloudWatch를 통한 로깅 설정

4. **AWS CodePipeline 연결**
   - GitHub 리포지토리를 소스 단계로 연결
   - 배포 단계에서 S3로 자동 업로드 설정

---
## 🛠 구축 순서 - 상세 및 진행상황
1. **웹사이트 제작**
   - `index.html` 파일을 이용해 정적 웹사이트 제작 (완료)

2. **GitHub 리포지토리 생성**
   - 소스 코드를 업로드하여 AWS에서 자동 배포할 수 있도록 준비 (완료)

3. **AWS 리소스 세팅**
**1) S3 버킷 생성 및 정적 웹 호스팅 설정
**- 버킷 이름 : smart-static-website-abby
- 버킷 정책:
- {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::smart-static-website-abby/*"
        }
    ]
}

  
**  2)  CloudFront 배포 생성 및 ACM 인증서 연결**     
🌍 CloudFront + HTTPS 보안 연결 구성
이 단계에서는 정적 웹사이트를 CloudFront를 통해 전 세계에 빠르게 전달하고,
ACM 인증서를 활용해 HTTPS 보안 연결을 적용합니다.

✅ 1. SSL 인증서 생성 (AWS Certificate Manager)
AWS Console에서 Certificate Manager (ACM) 이동
[인증서 요청] → 공개 인증서 선택
도메인 입력 (예: www.example.com)
DNS 검증 선택
제공된 CNAME 레코드를 DNS 설정에 추가
인증서 상태가 발급됨(Issued)으로 바뀌면 완료

✅ 2. CloudFront 배포 생성
AWS Console에서 CloudFront 이동 → [배포 만들기]
설정 항목:
오리진 도메인: S3 버킷 선택 또는 bucket-name.s3.amazonaws.com 입력
기본 루트 객체: index.html
프로토콜 정책: Redirect HTTP to HTTPS
SSL 인증서: 앞서 발급받은 ACM 인증서 선택
[배포 생성] 클릭 후 완료까지 수 분 소요
배포 완료 후, 도메인 주소 예시:
arduino
코드 복사
https://d123abcd.cloudfront.net
 

   - WAF 설정으로 보안 강화
   - CloudWatch를 통한 로깅 설정





---
## 🚀 배포 결과

- **URL**: [http://smart-static-website-abby.s3-website-us-east-1.amazonaws.com] 
(실제 도메인이 있다면 여기에 링크)

---

## 📁 프로젝트 구조
smart-static-website/ ├── index.html ├── README.md └── .github/ └── workflows/ # (CI/CD 관련 파일이 있다면)

yaml
코드 복사

---

## 📝 기타

- 이 프로젝트는 AWS 프리 티어를 기준으로 진행되었으며, 사용 시 비용에 유의해야 합니다.
- HTTPS 적용을 위해 AWS Certificate Manager에서 인증서를 요청하고 CloudFront에 연결해야 합니다.


