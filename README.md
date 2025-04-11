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

## 🚀 배포 결과

- **URL**: [https://www.example.com](https://www.example.com)  
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


