# SpringSequrity

Spring Sequrity 를 활용한 회원 로그인 / 로그아웃 처리 과정 구현

- 로그인 과정
  • 로그인 시도 -> username, password 정보를 HTTP body로 전달
  • 인증 관리 -> UserDetailsService 에게 username 을 전달하고 회원 상세정보를 요청
  • 회원 DB에서 회원 조회 -> 조회된 정보를 UserDatails로 변환
  • 인증 관리자가 인증 처리 -> UserDetailsService 가 전달해준 UserDetails의 정보와 클라이언트가 시도한     
    username,password 일치 여부 확인
  • UserDetails 의 password는 암호문이기에 클라이언트가 보낸 password를 암호화하여 비교


Spring Security란?
- 스프링 시큐리티는 스프링 기반 어플리케이션의 보안(인증과 권한, 인가)을 담당하는 스프링 하위 프레임워크
- 보안과 관련해서 체계적으로 많은 옵션들을 제공해주기 때문에 개발자 입장에서는 하나하나 보안 관련 로직을 작성하지 않아도 된다는 장점.


Spring Security 용어
  • 인증(Authentication) : 해당 사용자가 본인인지 확인하는 절차
  • 인가(Authoriztaion) : 인증된 사용자가 요청한 자웡네 접근 가능한지 결정하는 절차
  • 접근 주체(Principal) : 보호받는 Resource에 접근하는 대상
  • 비밀번호(Credential) : Resource에 접근하는 대상의 비밀번호
  • 권한 : 인증된 주체가 어플리케이션의 동작을 수행할 수 있도록 허락되어 있는지 결정
    - 인증 과정을 통해 주체가 증명된 이후 권한을 부여할 수 있다.
    - 권한 부여에 두 가지 영역이 존재하는데 웹 요청 권한과 메서드 호출 및 도메인 인스턴스에 대한 접근 권한 부여가 있다.

