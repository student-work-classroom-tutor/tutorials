# PyTorch 튜토리얼

모든 튜토리얼은 이제 다음 위치에서 스핑크스 스타일 문서로 제공됩니다.

## [https://pytorch.org/tutorials](https://pytorch.org/tutorials)

1. Python 파일을 만듭니다. 문서에 삽입하는 동안 실행하려면 접미사 `tutorial`을 붙여 파일을 저장하여 파일 이름을 `your_tutorial.py`로 지정합니다.
2. 난이도에 따라 `beginner_source`, `intermediate_source`, `advanced_source` 디렉터리 중 하나에 넣습니다. 레시피인 경우 `recipes_source`에 추가합니다. 불안정한 프로토타입 기능을 보여주는 튜토리얼의 경우 `prototype_source`에 추가합니다.
3. 튜토리얼의 경우(프로토타입 기능인 경우 제외) `toctree` 지시문에 포함하고 [index.rst](./index.rst)에 `customcarditem`을 만듭니다.
4. 튜토리얼(프로토타입 기능인 경우 제외)의 경우 `.. customcarditem:: beginner/your_tutorial.html`과 같은 명령을 사용하여 [index.rst 파일](https://github.com/pytorch/tutorials/blob/main/index.rst)에 썸네일을 만듭니다. 레시피의 경우 [recipes_index.rst](https://github.com/pytorch/tutorials/blob/main/recipes_source/recipes_index.rst)에 썸네일을 만듭니다.

Jupyter 노트북으로 시작하는 경우 [이 스크립트](https://gist.github.com/chsasank/7218ca16f8d022e02a9c0deb94a310fe)를 사용하여 노트북을 Python 파일로 변환할 수 있습니다. 변환하고 프로젝트에 추가한 후 섹션 제목과 기타 항목이 논리적 순서로 되어 있는지 확인하세요.

## 로컬 빌드

튜토리얼 빌드는 매우 크고 GPU가 필요합니다. 머신에 GPU 장치가 없으면 실제로 데이터를 다운로드하고 튜토리얼 코드를 실행하지 않고도 HTML 빌드를 미리 볼 수 있습니다.

1. `pip install -r requirements.txt`를 실행하여 필요한 종속성을 설치합니다.

> 일반적으로 `conda` 또는 `virtualenv`에서 실행합니다. `virtualenv`를 사용하려면 repo 루트에서 `virtualenv venv`를 실행한 다음 `source venv/bin/activate`를 실행합니다.

- GPU 기반 노트북이 있는 경우 `make docs`를 사용하여 빌드할 수 있습니다. 이렇게 하면 데이터가 다운로드되고 튜토리얼이 실행되며 설명서가 `docs/` 디렉터리에 빌드됩니다. GPU가 있는 시스템의 경우 약 60~120분이 걸릴 수 있습니다. 시스템에 GPU가 설치되어 있지 않으면 다음 단계를 참조하세요.
- `make html-noplot`을 실행하여 기본 HTML 문서를 `_build/html`에 빌드하여 계산 집약적인 그래프 생성을 건너뛸 수 있습니다. 이렇게 하면 튜토리얼을 빠르게 미리 볼 수 있습니다.

## 단일 튜토리얼 빌드

`GALLERY_PATTERN` 환경 변수를 사용하여 단일 튜토리얼을 빌드할 수 있습니다. 예를 들어 `neural_style_transfer_tutorial.py`만 실행하려면 다음을 실행합니다.

```
GALLERY_PATTERN="neural_style_transfer_tutorial.py" make html
```
또는

```
GALLERY_PATTERN="neural_style_transfer_tutorial.py" sphinx-build . _build
```

`GALLERY_PATTERN` 변수는 정규 표현식을 따릅니다.

## PyTorch 문서 및 튜토리얼에 기여하는 것에 관하여
* PyTorch 문서에 기여하는 것에 관한 정보는
PyTorch Repo [README.md](https://github.com/pytorch/pytorch/blob/master/README.md) 파일에서 찾을 수 있습니다.
