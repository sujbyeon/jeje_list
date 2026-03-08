

## 문제 분석

사용자의 스크린샷에서 비교 모달 제목("매물 비교 (10개)")과 닫기(×) 버튼만 보이고, "이미지 저장" / "엑셀 저장" 버튼이 보이지 않음. 현재 버튼이 제목과 같은 줄에 `flex justify-between`으로 배치되어 있어 화면 폭이 좁으면 가려지거나 줄바꿈 없이 숨겨질 수 있음.

## 해결 방안

**`src/components/CompareModal.tsx` 수정:**

1. 저장 버튼을 제목 아래 별도 줄로 분리하여 항상 보이도록 변경
2. 버튼 크기를 키우고 더 눈에 띄는 스타일 적용
3. 테이블 위, 제목 아래에 배치하여 확실하게 노출

변경 전:
```
<div className="flex items-center justify-between mb-6 pr-10">
  <h2>매물 비교</h2>
  <div className="flex gap-2">  ← 같은 줄에 버튼 (가려짐)
    ...
  </div>
</div>
```

변경 후:
```
<h2 className="mb-4 pr-10">매물 비교</h2>
<div className="flex gap-2 mb-6">  ← 별도 줄로 분리
  <button>📷 이미지 저장</button>
  <button>📊 엑셀 저장</button>
</div>
```

