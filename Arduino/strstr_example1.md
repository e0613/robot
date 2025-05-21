# C언어 strstr() 함수 기본 예제

## 함수 프로토타입
```c
char *strstr(const char *haystack, const char *needle);
```

## 설명
`strstr()` 함수는 문자열(`haystack`) 내에서 부분 문자열(`needle`)을 검색하여 찾습니다. 
- 부분 문자열이 발견되면 해당 위치의 포인터를 반환
- 발견되지 않으면 NULL을 반환

## 코드 예제

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char *str = "Hello, world! Welcome to C programming.";
    const char *substr = "world";
    
    // strstr() 함수로 부분 문자열 검색
    char *result = strstr(str, substr);
    
    if (result != NULL) {
        printf("부분 문자열을 찾았습니다: %s\n", result);
        printf("원본 문자열에서의 위치: %ld\n", result - str);
    } else {
        printf("부분 문자열을 찾지 못했습니다.\n");
    }
    
    return 0;
}
```

## 실행 결과
```
부분 문자열을 찾았습니다: world! Welcome to C programming.
원본 문자열에서의 위치: 7
```

## 코드 설명

1. 문자열 `str`과 검색할 부분 문자열 `substr`을 선언합니다.
2. `strstr()` 함수를 사용하여 `str` 내에서 `substr`을 검색합니다.
3. 검색 결과가 NULL이 아니면:
   - 찾은 위치부터 끝까지의 문자열을 출력합니다.
   - 원본 문자열의 시작 위치에서 얼마나 떨어져 있는지 계산하여 출력합니다.
4. 결과가 NULL이면 부분 문자열을 찾지 못했다는 메시지를 출력합니다.

## 주의사항
- 포인터 연산(`result - str`)은 문자열에서 부분 문자열이 시작되는 인덱스를 계산합니다.
- `strstr()` 함수는 대소문자를 구분합니다.
- 반환된 포인터는 원래 문자열(`str`)의 일부를 가리키므로, 원본 문자열이 변경되면 반환된 포인터의 내용도 변경됩니다.
