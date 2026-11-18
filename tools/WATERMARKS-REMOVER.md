# watermarks-remover (vendored)

- 출처: https://github.com/guillaumemeyer/watermarks-remover
- 커밋: 5a62be6338d2812372b1da440e55c82922f97d53 (2026-11-01), MIT 라이선스
- 스킬: `.claude/skills/remove-ai-marks`, `.claude/skills/clean-user-facing-text`

## 서비스 실행 (remove-ai-marks에 필요)

```bash
cd tools/watermarks-remover
python3 service/scripts/server.py   # 127.0.0.1:8765
curl --noproxy '*' http://127.0.0.1:8765/health
```

- 이미지·문서 메타데이터 정리는 LLM 없이 동작합니다.
- 서비스의 텍스트 `/clean`은 LLM 재작성 백엔드(WATERMARKS_REWRITE_*)가 없으면 실패합니다.
  숨은 유니코드만 지우려면:
  `python3 .claude/skills/clean-user-facing-text/scripts/clean_text.py 파일.txt`
