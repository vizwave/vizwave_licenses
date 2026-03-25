# vizwave_licenses

Vizwave 제품군의 암호화된 라이선스 파일을 호스팅하는 저장소.

## 구조

```
licenses/
  {MODEL}.bin    # Ed25519 서명 + AES-256-GCM 암호화된 라이선스 파일
```

## 보안

- **Ed25519 서명**: 발급자 private key로 서명하여 위조 방지
- **AES-256-GCM 암호화**: 대칭키로 암호화하여 내용 비공개 (시리얼 번호 등)
- 평문 JSON은 저장소에 포함되지 않음

## 배포

GitHub Release `latest` 태그를 통해 배포. 클라이언트는 Release asset URL로 다운로드.

```
https://github.com/vizwave/vizwave_licenses/releases/download/latest/{MODEL}.bin
```

## 검증

클라이언트(dB Amero 등)는 내장된 Ed25519 public key + AES 대칭키로 복호화 및 서명 검증 후 라이선스를 적용한다.
복호화 또는 서명 검증 실패 시 라이선스 없음으로 처리.
