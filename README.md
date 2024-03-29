 <h3 align="center">Keyboard Changer</h3>
  <p align="center">










## Table of Contents

- [About the Project](#about-the-project)

  - [Built With](#built-with)

- [Getting Started](#getting-started)

  - [Installation](#installation)
    - [Download](#download)
    - [Build](#build)
    - [Run](#run)
    - [Run Script](#run-script)

- [Usage](#usage)

- [API](#api)

- [License](#license)

  <!-- ABOUT THE PROJECT -->



## About The Project

	다들 한영키가 고장 나거나 기타 오류로 한글이 입력이 되지 않아 당황스러운 경우가 있었을 것 입니다. 저희는 또한 이런 경우가 있었고 이에 아이디어를 얻어 영어로 한글문장을 입력하면 한글로 출력하는 프로젝트를 기획하였습니다.
	
	또한 일본어도  일본어 로마자 표기법에 근거하여 같은 발음의 일본어로 출력이 가능합니다.

### Built with

- Java (version 11)
- Kotlin (version 1.3.50)
- Gradle



<!-- GETTING STARTED -->

## Getting Started

<!-- INSTALLATION -->

### Installation

<!-- DOWNLOAD -->

#### Download

```sh
git clone https://github.com/kdPark0723/KeyboardChanger
```

<!-- BUILD -->

#### Build

```sh
sudo bash ./gradlew --scan build
```

<!-- RUN -->

#### Run

```sh
java -jar build/libs/KeyboardChanger-0.0.1-SNAPSHOT.jar
```

<!-- RUN SCRIPT -->

#### Run Script

```sh
git clone https://github.com/kdPark0723/KeyboardChanger
cd KeyboardChanger

sudo bash ./gradlew --scan build
java -jar build/libs/KeyboardChanger-0.0.1-SNAPSHOT.jar
```



<!-- USAGE EXAMPLE -->

## Usage

#### ENG -> KOR

	한글을 입력해야하지만 한영키가 고장났을 때 혹은 오류로 인하여 한글 입력이 불가능할 때 유용하게 사용이 가능합니다. 

1. Run Script 까지 진행 후 웹 브라우저를 연다.

2. 검색 창에 "localhost:3000/korean/[변환하고 싶은 글자]?type=en" 를 입력한다.

   (ex: dkssudgktpdy 입력)

   ![image](https://user-images.githubusercontent.com/50135193/70551021-1184bc00-1bba-11ea-89db-0aeed003a190.png)

3. 결과 값이 브라우저 화면에 출력된다.





```
일본어 입력이 불가능할때 일본어 로마자 표기법에 근거하여 영어로 일본어 발음과 동일하게 입력 시 일본어 출력이 가능합니다.
```

#### ENG -> JPN

1. Run Script 까지 진행 후 웹 브라우저를 연다.

2. 검색 창에 "localhost:3000/japanese/[변환하고 싶은 글자]?type=en" 를 입력한다.

   (ex: arigato 입력)

   ![image](https://user-images.githubusercontent.com/50135193/70612017-7affdb80-1c49-11ea-9469-b019eead1c3f.png)

3. 결과 값이 브라우저 화면에 출력된다.

   * 띄어쓰기 입력시 띄어쓰기를 기준으로 가타카나로 나타내준다

     ![image](https://user-images.githubusercontent.com/50135193/70622122-8f9a9e80-1c5e-11ea-8e93-bf45f6588c24.png)

     

<!-- API-->

## API
### 한글 변환
#### 1.API 기본정보

| API명           | 메서드 | 요청 URL                       | 출력 포맷 |
| --------------- | ------ | :----------------------------- | --------- |
| keyboardchanger | GET    | localhost:3000/korean/{value}?type | JSON      |

#### 2. 요청변수

| 요청변수명 | 타입   | 필수 여부 | 설명                                        |
| ---------- | ------ | :-------- | ------------------------------------------- |
| value       | string | Yes       | 변환될 값 |
| type       | string | Yes       | value의 값(ex: en) |


#### 3. 응답결과

| 필드  | 타입   | 설명                                       |
| ----- | ------ | ------------------------------------------ |
| value | string | 변환된 값 출력                           |
| type  | string | KOREAN |

#### 4. 응답코드

| 상태          | HTTP 코드 | 출력메세지             |
| ------------- | --------- | ---------------------- |
| 성공          | 200       |                        |
| 입력언어 오류 | 403       | Unsupported type error |
| 미입력        | 404       | No matching handler    |


### 일본어 변환
#### 1.API 기본정보

| API명           | 메서드 | 요청 URL                       | 출력 포맷 |
| --------------- | ------ | :----------------------------- | --------- |
| keyboardchanger | GET    | localhost:3000/japanese/{value}?type | JSON      |

#### 2. 요청변수

| 요청변수명 | 타입   | 필수 여부 | 설명                                        |
| ---------- | ------ | :-------- | ------------------------------------------- |
| value       | string | Yes       | 변환될 값 |
| type       | string | Yes       | value의 값(ex: en) |

#### 3. 응답결과

| 필드  | 타입   | 설명                                       |
| ----- | ------ | ------------------------------------------ |
| value | string | 변환된 값 출력                           |
| type  | string | JAPANESE |

#### 4. 응답코드

| 상태          | HTTP 코드 | 출력메세지             |
| ------------- | --------- | ---------------------- |
| 성공          | 200       |                        |
| 입력언어 오류 | 403       | Unsupported type error |
| 미입력        | 404       | No matching handler    |

<!-- LICENSE -->

## License

 This project is licensed under the MIT License.  See `LICENSE` for more information.





