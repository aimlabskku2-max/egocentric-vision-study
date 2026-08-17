# Egocentric Vision Study — AIM LAB

GitHub Pages로 배포하는 정적 사이트입니다.

## 올리는 방법
1. GitHub에서 새 저장소 생성 (Public).
2. 이 폴더의 파일 전체를 저장소 루트에 업로드 — index.html, support.js, links.json, assets/
3. 저장소 Settings → Pages → Source: "Deploy from a branch" → Branch: main / (root) → Save
4. 1~2분 후 https://<사용자명>.github.io/<저장소명>/ 에서 확인

## 자료 링크 수정
links.json 만 편집하면 됩니다. GitHub 웹에서 links.json 열기 → 연필 아이콘 → Commit 하면 1~2분 내 반영됩니다.

각 주차의 형식:

```jsonc
{
  "week": "3주차",
  "title": "...",
  "gloss": "...",
  "summary": "...",
  "slides": [
    { "label": "PDF 1", "name": "JaeSeung Kim", "url": "https://drive.google.com/uc?export=download&id=파일ID" }
  ],
  "video": { "type": "zoom", "url": "https://....zoom.us/rec/share/...", "password": "암호" }
}
```

- slides: 파일 목록. label은 표에 뜨는 짧은 텍스트, name(선택)은 상세 페이지 버튼에 뜨는 설명(발표자 등). 빈 목록 []이면 "준비 중"으로 표시됩니다.
- slides url은 클릭 즉시 다운로드되는 `https://drive.google.com/uc?export=download&id=파일ID` 형식을 권장합니다. 파일ID는 Drive 공유 링크의 `/d/`와 `/view` 사이 문자열입니다.
- video: 드라이브에 올린 영상은 `{ "type": "drive", "url": "https://drive.google.com/file/d/파일ID/view" }` (클릭 시 재생, 다운로드 버튼 제공). 줌 클라우드 녹화는 `{ "type": "zoom", "url": "...", "password": "..." }` — 사이트에 암호가 표시되고 링크/암호 복사 버튼이 붙습니다. 없으면 `null`. 드라이브 영상은 상세 페이지에 플레이어가 임베드되며, 새 탭 재생·다운로드 링크가 함께 표시됩니다.
- readings(선택): [{ "title": ..., "venue": ..., "note": ..., "url": ... }] 목록 — 상세 페이지에 논문 리스트로 표시됩니다.
- 예전처럼 slides / video에 URL 문자열 하나만 넣어도 동작합니다.
- 새 파일을 올릴 땐 Drive에서 공유 설정이 "링크가 있는 모든 사용자"인지 확인하세요.
