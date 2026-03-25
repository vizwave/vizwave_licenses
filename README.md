# vizwave_licenses

Vizwave 제품군의 서명된 라이선스 파일을 호스팅하는 저장소.

## 구조

```
licenses/
  {MODEL}.json        # 모델별 라이선스 JSON (평문)
  {MODEL}.json.sig    # Ed25519 detached 서명 (base64)
```

## 배포

GitHub Release를 통해 배포. 클라이언트는 Release asset URL로 다운로드.

```
https://github.com/vizwave/vizwave_licenses/releases/download/{tag}/{filename}
```

## 검증

클라이언트(dB Amero 등)는 내장된 Ed25519 public key로 서명을 검증한 후 라이선스를 적용한다.
서명 검증 실패 시 라이선스 없음으로 처리.
