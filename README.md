# 🦞 Hello Claw - Frontend

S3 + CloudFront로 서빙되는 정적 프론트엔드.

## 구성

- 계산기 🧮
- 스네이크 게임 🐍
- 백엔드 연결 상태 패널 🔗

## 배포

S3 버킷에 업로드 → CloudFront 캐시 무효화:

```bash
aws s3 cp index.html s3://BUCKET_NAME/index.html --content-type "text/html; charset=utf-8"
aws cloudfront create-invalidation --distribution-id CF_ID --paths "/*"
```

## 인프라

- **S3**: 정적 파일 호스팅
- **CloudFront**: HTTPS + CDN + EC2 프록시 (`/api/*`)
- **URL**: https://d2q4tbki66r57f.cloudfront.net
