#Security login user

###SpringContextHolder
````java
Authentication authentication = SecurityContextHolder.getContext().getAuthentication();
System.out.println(authentication.getName());
````
````java
@RequestMapping("/")
    public String index(Principal principal) {
        System.out.println(principal.getName());
        return "index";
    }
````
````java
User user = (User) SecurityContextHolder.getContext().getAuthentication().getPrincipal();
System.out.println(user.getUsername());
````
- http://chomman.github.io/blog/spring%20framework/spring-security%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%98%EC%97%AC-%EC%82%AC%EC%9A%A9%EC%9E%90%EC%9D%98-%EC%A0%95%EB%B3%B4%EB%A5%BC-%EC%B0%BE%EB%8A%94-%EB%B0%A9%EB%B2%95/