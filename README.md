# Whisper + Pyannote 음성 전사 및 화자 분리

- OpenAI Whisper와 Pyannote.audio를 결합하여 음성 파일을 텍스트로 변환하고, 각 발화에 화자를 자동으로 구분하여 할당하는 프로젝트입니다.
- 한국어 -> 한글
- api 미사용, 무료

## 📌 주요 기능

- **음성 인식(STT)**: Whisper를 사용한 고품질 음성-텍스트 변환
- **화자 분리(Speaker Diarization)**: Pyannote를 통한 자동 화자 구분
- **발화 병합**: 같은 화자의 연속된 짧은 발언을 자연스럽게 병합
- **다양한 출력 형식**: TXT 및 SRT 자막 파일로 결과 저장

## 🚀 실행 환경

이 프로젝트는 **Google Colab** 환경에서 실행되도록 설계되었습니다.

### 권장 사양
- Google Colab (무료 버전 가능)
- GPU 런타임 (화자 분리 속도 향상, 필수는 아님)
- Python 3.x

## ⚠️ 사전 준비 (필수)

Pyannote 모델을 사용하려면 Hugging Face 토큰이 필요합니다.

### 토큰 발급 절차
1. **[Hugging Face](https://huggingface.co)** 에서 계정 생성
2. **[Pyannote 모델 페이지](https://huggingface.co/pyannote/speaker-diarization-3.1)** 접속 후 약관 동의 체크
3. **[토큰 페이지](https://huggingface.co/settings/tokens)** 에서 액세스 토큰 발급
4. 노트북의 5단계에서 `YOUR_HF_TOKEN_HERE`를 발급받은 토큰으로 교체

> ⚠️ **중요**: 약관 동의 없이는 모델을 다운로드할 수 없습니다!

## 📖 사용 방법

1. `whisper_pyannote.ipynb` 파일을 Google Colab에서 열기
2. 런타임 → GPU로 변경 (선택사항)
3. 셀을 순서대로 실행:
   - 1단계: 패키지 설치
   - 2단계: 음성 파일 업로드
   - 3단계: WAV 형식으로 변환
   - 4단계: Whisper로 음성 인식
   - 5단계: Pyannote로 화자 분리 (토큰 입력 필수)
   - 6단계: 결과 병합 및 저장

## 📁 출력 파일

실행이 완료되면 다음 파일들이 생성됩니다:

- `{원본파일명}_transcript.txt`: 화자 구분이 포함된 텍스트 파일
- `{원본파일명}_transcript.srt`: 타임스탬프 포함 자막 파일 (영상 편집용)

## 🎯 지원 오디오 형식

- M4A, MP3, WAV 등 ffmpeg가 지원하는 모든 오디오 형식

## 📝 라이선스

이 프로젝트는 사용된 라이브러리들의 라이선스를 따릅니다:
- OpenAI Whisper: MIT License
- Pyannote.audio: MIT License
