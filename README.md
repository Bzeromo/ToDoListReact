# Context API
    - 컴포넌트는 트리 구조로 이루어져있다. 
    트리 레벨이 깊어졌을 때 다른 컴포넌트로 prop을 넘기려면 목적지까지 계속해서 다른 컴포넌트를 통해 prop을 넘겨야한다. (Prop Drilling)
    이 Prop Drilling 문제를 해결하는 방법 중 하나가 Context API이다.

    - Context Provider: 데이터를 제공하고 관리한다.
    - Context Consumer: 데이터를 수령하여 처리한다.
    - Provider가 정보를 넘겨받고 업데이트되면 반응형에 의해 Consumer가 다시 연산하기 시작한다.
    - 이 두 가지를 이용하면 멀리 떨어져있는 컴포넌트에게도 쉽게 prop을 넘길 수 있다.
    - 단, 남발하면 성능 저하의 우려가 있다. (Provider가 변화하면 Consumer와 관련된 컴포넌트들이 전부 다시 렌더링하기 때문이다.)
    - 그리고 Consumer가 있으면 반드시 Provider도 존재해야 하기 때문에 독립성의 문제 역시 제기된다.
    (컴포넌트를 한 번 감싼 컴포넌트를 만드는 형태로 해결할 수 있다.)

# To Do App에 적용하기
    - To do 컴포넌트에서 이벤트가 발생하여 데이터가 조작될 때 전체적으로 데이터를 관리하기 위해서 다른 컴포넌트에 prop을 계속 넘겨주거나 이벤트를 던져야하는데 이를 편하게 하기 위해 Context API를 사용한다.
    - 원하는 Todo를 타이핑하고 추가 버튼을 누르면 Todo가 리스트에 추가된다.
    - 로컬 스토리지가 연결되어 새로고침을 하거나 창을 닫아도 데이터가 삭제되지 않는다.
    - 토글 버튼을 누르면 취소선이 생기며 오늘 끝낸 일을 나타낼 수 있다.
    - 삭제 버튼을 통해 Todo를 삭제할 수 있다.

> uuid: 겹치지 않는 id를 생성해주는 라이브러리
