# LLVM-Korean

LLVM Project 의 튜토리얼 문서를 중심으로 하여 기초 가이드를 한국어로 작성해보기 위한 프로젝트

- Getting Started : https://llvm.org/docs/GettingStarted.html
- Tutorial : https://llvm.org/docs/tutorial/

<br>

# Getting Started

```bash
git clone https://github.com/llvm/llvm-project.git

cd llvm-project
cmake -S llvm -B build -G <generator> [options]
```

### cmake args
- -S : CMakeList.txt 파일이 존재하는 디렉토리 경로 (CmakeList.txt 파일이 빌드 파일을 생성할 핵심 파일)

- -B (--build) : 빌드 파일이 생성될 디렉토리 경로

- -G : 빌드 시스템의 generator 지정 (e.g. Ninja, UNIX Makefiles, Visual Studio, Xcode)

- -target : LLVM Project 전체가 아닌 필요한 부분만 빌드하도록 설

### common options
- -DLLVM_ENABLE_PROJECTS : 추가로 빌드하고자 하는 LLVM subprojects 를 세미콜론(;) 으로 구분지어 작성  
  (e.g. lang, clang-tools-extra, lldb, lld, polly, or cross-project-tests)
  
- -DCMAKE_INSTALL_PREFIX : LLVM 라이브러리 파일이 설치될 디렉토리 경로 (default /usr/local)

- -DCMAKE_BUILD_TYPE : 최적화 및 디버깅 level 지정 ([Release, Debug, RelWithDebInfo, MinSizeRel](https://llvm.org/docs/CMake.html#cmake-build-type))

- -DLLVM_ENABLE_ASSERTIONS=ON/OFF : assertion check 사용여부 (default ON for Debug, OFF for Release/RelWithDebInfo/MinSizeRel)
  
- -DLLVM_USE_LINKER=lid : LLD 링커 사용 (설치 필요)
  
- -DLLVM_PARALLEL_{COMPILE,LINK,TABLEGEN}_JOBS=N : 동시에 실행 가능한 job 의 최대 수 지정

```bash

```


<br>

# Index

- IR : [Intermediate Representation](https://en.wikipedia.org/wiki/Intermediate_representation)
- CMake : OS 등 환경에 관계 없이 빌드 파일 (e.g. Makefile, Visual Studio 프로젝트) 을 자동으로 생성 ([github](https://github.com/Kitware/CMake))
- Ninja : 속도에 강점이 있는 CMake generator ([github](https://github.com/ninja-build/ninja))
- LLD : LLVM Project 에서 제공하는 고성능 링커 ([Docs](https://lld.llvm.org/))
