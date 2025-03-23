# 랭체인(LangChain) 쉽게 시작하기

## 1. 랭체인이란?

랭체인은 여러 인공지능 언어 모델을 연결해서 복잡한 일을 쉽고 효율적으로 처리할 수 있도록 도와주는 도구입니다. 챗GPT와 같은 언어 모델을 더 똑똑하게 활용하여 챗봇이나 자동 글 요약 시스템 등을 개발할 수 있습니다.

특히 랭체인은 다음과 같은 작업을 도와줍니다:

- 작업을 순서대로 연결하는 '체인(Chain)'
- 스스로 일을 처리하는 '에이전트(Agent)'
- 대화를 기억하고 활용하는 '메모리(Memory)'

주로 챗봇 개발, 자동 문서 요약, 데이터 기반의 질문답변 시스템 구축 등 다양한 분야에 사용됩니다.

## 2. 랭체인의 핵심 개념

- **체인(Chain)**: 여러 작업을 연결하여 하나의 흐름을 만드는 개념입니다. 예를 들어, 질문에 대한 답을 찾고 요약한 뒤 다시 전달하는 과정을 자동화할 수 있습니다.
- **에이전트(Agent)**: 목표를 이루기 위해 외부 도구나 API를 사용하여 스스로 행동을 결정하고 처리하는 모듈입니다.
- **메모리(Memory)**: 이전의 대화나 결과를 기억하여 연속된 작업이나 대화를 자연스럽게 진행할 수 있도록 합니다.
- **프롬프트 템플릿(Prompt Template)**: 언어 모델이 원하는 결과를 정확히 이해하도록 미리 만든 질문 형식입니다.

## 3. 준비물

- Python 3.8 이상 ([공식 홈페이지](https://www.python.org/)에서 설치 가능)
- 주요 라이브러리: LangChain, OpenAI, Hugging Face, FastAPI
- IDE: Visual Studio Code 또는 PyCharm 추천
- [LangChain 공식 GitHub 페이지](https://github.com/langchain-ai/langchain)
- Git 설치

## 4. 개발 환경 설정하기

### 파이썬 설치 확인

- 먼저 Python을 설치하고 버전을 확인합니다.

**Windows:**

```bash
python --version  # 파이썬 버전 확인
```

**macOS:**

```bash
python3 --version  # 파이썬 버전 확인
```

### 가상 환경 설정

가상 환경을 사용하면 각 프로젝트별로 필요한 라이브러리를 독립적으로 관리할 수 있습니다.

**Windows:**

```bash
python -m venv langchain-env  # 가상 환경 생성
langchain-env\Scriptsctivate  # 가상 환경 활성화
```

**macOS:**

```bash
python3 -m venv langchain-env  # 가상 환경 생성
source langchain-env/bin/activate  # 가상 환경 활성화
```

### 라이브러리 설치

활성화된 가상 환경에서 필요한 라이브러리를 설치합니다.

```bash
pip install langchain openai huggingface_hub fastapi  # 필수 라이브러리 설치
```

### 설치 확인하기

라이브러리가 잘 설치되었는지 확인합니다.

```bash
pip list  # 설치된 라이브러리 확인
```

### 간단한 코드로 테스트하기

IDE에서 다음과 같은 간단한 코드를 작성하여 Python과 랭체인이 정상적으로 작동하는지 확인합니다.

```python
from langchain.prompts import PromptTemplate

prompt = PromptTemplate(
    input_variables=["name"],
    template="Hello, {name}! 랭체인이 잘 작동하고 있어요!"
)

print(prompt.format(name="glshlee"))
```

위 코드를 실행했을 때 아래와 같은 메시지가 출력된다면 설정이 성공한 것입니다.

```
Hello, glshlee! 랭체인이 잘 작동하고 있어요!
```
