# Team MOA Widget Updates

이 저장소는 Team MOA 위젯의 자동 업데이트 manifest만 관리합니다. 앱 전체 코드와 실행 파일은 저장소에 올리지 않습니다.

## 저장소에 올리는 파일

```text
updates/manifest.json
README.md
```

## GitHub Release에 올리는 파일

```text
Team-MOA-win.zip
```

## 새 버전 배포 순서

1. 위젯 폴더의 앱 버전을 올립니다.
   - `resources/app/src/main.js`의 `APP_VERSION`
   - `resources/app/package.json`의 `version`
2. `Team-MOA-win` 폴더를 `Team-MOA-win.zip`으로 압축합니다.
3. GitHub에서 새 Release를 만듭니다.
   - Tag: `v0.1.21`
   - Asset: `Team-MOA-win.zip`
4. `updates/manifest.json`을 새 버전에 맞게 수정합니다.
5. 이 저장소에는 `updates/manifest.json`만 commit/push합니다.

## manifest 형식

```json
{
  "version": "0.1.21",
  "url": "https://github.com/ferrariclec16/team-moa-widget-updates/releases/download/v0.1.21/Team-MOA-win.zip",
  "notes": "상단 직원 실적 바 추가, adminmoa 실적 연동, Google Apps Script 백엔드 제거, 업데이트 방식 개선."
}
```

직원 PC의 위젯은 `updates/manifest.json`을 확인하고, 새 버전이 있으면 업데이트 버튼에 알림을 표시합니다.
