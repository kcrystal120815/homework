# Avatars 과제

** 아직 레이아웃을 제대로 구현하지 못한 상황이지만 우선 제출합니다. 더 연구해 보겠습니다. **

## HTML

** 과제 조건 중 '상태 정보'에 관련해서는 최대한 시도해 보았습니다. 하지만 '성능 최적화' 부분은 lazy loading밖에 생각할 수 없었는데, 스크롤을 많이 내려야 하는 페이지가 아니라서 그런 방식이 의미가 있지 않을 것 같다고 생각해 제외했습니다. **

```
<!DOCTYPE html>
<html lang="ko-KR">
** 언어 한국어로 설정 **
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Avatars| Homework</title>
    ** 제목 Avatars 지정 **
    <link rel="stylesheet" href="./styles/avatars.css" />
    ** CSS 연결 **
  </head>
  <body>
    <header>
      <nav>
        <ul class="menu">
          <button>Avatars</button>
        </ul>
        ** 다른 버튼들이 생긴다면 li로 묶을 생각으로 ul로 지정했습니다. **
      </nav>
      ** 메뉴 탭 같은 기능인 것 같아서 header에 넣고 navigation 사용했습니다. **
    </header>
    <main>
      <section id="activity-status" aria-label="각 유저들의 활동 상태 확인">
      ** 접근성 고려해서 aria-label 사용했습니다. **
        <p>
        ** 이미지를 두 줄로 보이도록 하는 게 계속 안 되고 있는 상황입니다. 혹시 도움이 될까 싶어서 p로 4개씩 구분해 보았습니다. **
        <figure class="user-avatar">
          <img src="./../assets/avatars/face1.jpg" alt="유저 1" />
          ** 이미지 src 연결하고 alt 사용해서 대체택스트 입력했습니다. **
          <span class="status-offline"></span>
          ** span 사용하는 게 맞을지 모르겠지만 적당히 표현할 요소를 찾지 못해서 span 사용했습니다. **
          <figcaption>유저 1은 외출 중입니다.</figcaption>
          ** 활동, 외출이 online, offline보다 조금 더 쉬운 말일 것 같아서 바꿔봤습니다. **
          ** 상태가 고정되어 있으면 의미가 없을 것 같아서 span class와 figcaption이 실제 상태에 따라서 같이 변화할 수 있도록 하고 싶었는데, 다른 방법을 찾지 못했습니다. **
        </figure>
        ** 접근성 고려해서 figcaption 넣으려고 figure 사용했습니다. **
        <figure class="user-avatar">
          <img src="./../assets/avatars/face2.jpg" alt="유저 2" />
          <span class="status-online"></span>
          <figcaption>유저 2는 활동 중입니다.</figcaption>
        </figure>
        <figure class="user-avatar">
          <img src="./../assets/avatars/face3.jpg" alt="유저 3" />
          <span class="status-offline"></span>
          <figcaption>유저 3은 외출 중입니다.</figcaption>
        </figure>
        <figure class="user-avatar">
          <img src="./../assets/avatars/face4.jpg" alt="유저 4" />
          <span class="status-online"></span>
          <figcaption>유저 4는 활동 중입니다.</figcaption>
        </figure>
        </p>
        <p>
        <figure class="user-avatar">
          <img src="./../assets/avatars/face5.jpg" alt="유저 5" />
          <span class="status-online"></span>
          <figcaption>유저 5는 활동 중입니다.</figcaption>
        </figure>
        <figure class="user-avatar">
          <img src="./../assets/avatars/face6.jpg" alt="유저 6" />
          <span class="status-online"></span>
          <figcaption>유저 6은 활동 중입니다.</figcaption>
        </figure>
        <figure class="user-avatar">
          <img src="./../assets/avatars/face7.jpg" alt="유저 7" />
          <span class="status-offline"></span>
          <figcaption>유저 7은 외출 중입니다.</figcaption>
        </figure>
        <figure class="user-avatar">
          <img src="./../assets/avatars/face8.jpg" alt="유저 8" />
          <span class="status-offline"></span>
          <figcaption>유저 8은 외출 중입니다.</figcaption>
        </figure>
        </p>
        ** 이미지 1과 같은 방법으로 이미지 8개 만들었습니다. **
      </section>
    </main>
    ** footer는 굳이 필요하지 않을 것 같아서 지웠습니다. **
  </body>
</html>
```

## CSS

** float를 사용하는 게 무슨 의미인지 열심히 검색을 해 봤지만.. 제가 제대로 사용한 게 맞는지 모르겠습니다. 그리고 Fiqma에 사이즈 등의 정보가 있다고 말씀하셨는데 찾지 못해서 Notion에 없는 부분은 임의로 설정했습니다. **

```
button { ** 상단 버튼에 대한 디자인 **
background-color: white; ** 버튼 배경 색상 **
border-radius: 4px; ** 모서리 둥근 사각형 **
border-width: 1px; ** 모서리 선 두께 **
padding-top: 2px; ** 위 여백 **
padding-bottom: 2px; ** 아래 여백 **
}

body { ** body 영역 전체에 대한 디자인 **
  height: 100%; ** 전체 화면 높이 100으로 설정 **
  margin: 0; ** 기본 여백 제거. 왜 필요한지는 잘 모르겠습니다. **
  background-color: whitesmoke; ** 배경 그라디언트를 넣고 싶었는데 그런 것까지 신경쓸 수 있는 상황이 아니어서 우선 색상으로 넣었습니다.**
}

#activity-status { ** Avatars 이미지와 '상태 표시 동그라미'를 포함한 영역에 대한 디자인 **
position: absolute; ** 절대 위치 **
top: 50%; ** 세로 중앙 **
left: 50%; ** 가로 중앙 **
transform: translate(-50%, -50%); ** 중앙으로 이동. 왜 top left 만으로는 안 되는 것인지 모르겠지만 필요하다고 해서 넣었습니다. **
width: 100%; ** 전체 화면 넓이 100으로 설정**
max-width: 800px; ** 최대 너비 제한. 왜 제한이 필요한지는 모르겠습니다.**
}

p { ** p 요소에 대한 디자인 **
  overflow: hidden; ** 내부 float 해제를 위한 clearfix라고 하는데, 이해하지 못했습니다.**
  margin: 0; ** 기본 여백 제거. 필요한 이유는 모르겠습니다. **
}

.user-avatar { ** Avatars 이미지에 대한 전체적인 디자인 **
float: left; ** 왼쪽으로 정렬하는 것이라고 하는데, 뭐가 정렬이 된 건지 모르겠습니다. **
width: 25%; ** 4개씩 한 줄에 배치되도록 하기 위해서 각 이미지의 너비를 25%로 합니다. 챗GPT의 도움을 받은 부분인데 의도대로 나오지도 않고, 아직 완전하게 이해하지도 못한 것 같습니다. **
box-sizing: border-box; ** 각 이미지의 사이즈를 계산할 때 여백과 테두리를 포함 **
margin-bottom: 20px; ** 과제 조건: 각 이미지 간의 간격 20px **
margin-right: 20px; ** 과제 조건: 각 이미지 간의 간격 20px **
position: relative; ** '상태 표시 동그라미'의 자리를 고려하여 상대적인 위치로 설정 **
}

.user-avatar img { ** Avatars 이미지 각각의 디자인 **
width: 64px; ** 과제 조건: 아바타 이미지 크기 64px **
height: 64px; ** 과제 조건: 아바타 이미지 크기 64px **
border-radius: 50%; ** 이미지 원으로 만들기 **
object-fit: cover; ** 비율 일정하게 잘리도록 **
}

.user-avatar:nth-child(4n){ ** 4번째 이미지에 대한 디자인**
  margin-right: 0; ** 오른쪽 여백 제거. 챗GPT의 도움을 받은 부분인데 정렬이 의도대로 되지 않고 있는 상황이라 필요한 이유를 모르겠습니다. **
}

figcaption { ** figcaption에 대한 디자인 **
display: none; ** 글자가 화면에 보이지 않도록 **
}

.status-online,
.status-offline { ** '상태 표시 동그라미'에 대한 디자인 **
position: absolute; ** 절대적인 위치 설정 **
bottom: 4px; ** 이미지 아래쪽에 위치하도록 liveserver를 확인하며 위치를 조정했습니다. **
right: 132px; ** 이미지 오른쪽에 위치하도록 liveserver를 확인하며 위치를 조정했습니다. **
width: 12px; ** 너비. 임의로 설정했습니다. **
height: 12px; ** 높이. 임의로 설정했습니다. **
border-radius: 50%; ** 원 모양 만들기 **
border-color: white; ** 테두리 색.. 을 넣긴 했는데 안 보이는 것 같습니다. 테두리 선 두께를 지정하지 않아서 안 보이는 것으로 짐작하고 있습니다.**
}

.status-online { ** 활동 중인 경우의 '상태 표시 동그라미'에 대한 디자인 **
background-color: #4cfe88; ** 원 배경 색상 **
}

.status-offline { ** 외출 중인 경우의 '상태 표시 동그라미'에 대한 디자인 **
background-color: #dbdbdb; ** 원 배경 색상 **
}
```

> 피드백

- `README.md` 파일에서 `avatars.md` 파일로 연결되는 `링크`가 `누락`됨. 현재는 `avatars.html` 파일로 연결되어 있어 링크를 클릭할 경우 HTML 코드만 확인 됨.
- <button> 요소의 type 속성이 생략되었음. type을 생략하면 submit임 해당 버튼을 클릭했을 때 서버로 데이타를 보낼 목적이었는지 고민해 봐야 함.
  단순히 버튼 처럼 디자인 되어 있다고 해서 <button>으로 마크업했다면 콘텐츠에 대한 고민이 부족한 것으로 보여짐.
- `<section> 요소`를 사용했다면 이를 고려하여 `적절한 제목`을 제공하는 것이 필요함.
- `“유저 1”`이라는 대체 텍스트가 적절한가에 대해 고민해보기 바람.
  만약 해당 대체 텍스트가 실제 사용자의 아바타로 사용될 경우 사용자의 이름이나 닉네임 등으로 수정될 가정을 하였다면 좋겠지만 디자인만을 생각하고 순서를 매기는 형태로 접근한 것이라면 이 역시 해당 서비스를 사용하는 사용자에 대한 고민이 부족한 것으로 보여짐.
- `jpg` 형식의 이미지를 제공하는 것이 `성능` 관점에서 최선이었을지 고민해보기 바람.
- `<img> 요소`에 `width`와 `height` 속성을 추가한다면 렌더링 성능 관점에서 이점이 있음.
- CSS를 사용한 스타일링 시 id 선택자는 될 수 있다면 `지양` 하는 것을 권장 함.
- flex를 지원하지 않는 환경에서 float을 사용한 방법이 적용되도록 하는 것이 필요한데 현재는 `float` 로만 구현되어 있음.
- 저장소를 배포하고 과제를 바로 확인할 수 있는 `링크`를 제공한 점이 인상적임.
