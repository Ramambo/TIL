# 💻 개발 메소드 정리

이 페이지는 자주 사용하는 프로그래밍 메소드와 함수들을 분야별로 정리하여 빠르게 참조할 수 있도록 합니다.

## 목차
- [Java](#java)
- [JavaScript](#javascript)
- [Python](#python)
- [Spring Framework](#spring-framework)
- [SQL](#sql)
- [알고리즘 관련 메소드](#알고리즘-관련-메소드)
- [기타 유용한 메소드](#기타-유용한-메소드)

---

## Java

### String 관련 메소드
| 메소드 | 설명 | 예시 |
|-------|------|------|
| `length()` | 문자열의 길이 반환 | `"hello".length()` → `5` |
| `charAt(int index)` | 특정 위치의 문자 반환 | `"hello".charAt(1)` → `'e'` |
| `substring(int beginIndex, int endIndex)` | 부분 문자열 반환 | `"hello".substring(1, 3)` → `"el"` |
| `indexOf(String str)` | 문자열의 위치 반환, 없으면 -1 | `"hello".indexOf("el")` → `1` |
| `replace(CharSequence target, CharSequence replacement)` | 문자열 치환 | `"hello".replace("l", "r")` → `"herro"` |
| `split(String regex)` | 문자열을 구분자로 분리하여 배열 반환 | `"h,e,l,l,o".split(",")` → `["h","e","l","l","o"]` |
| `toUpperCase()` / `toLowerCase()` | 대소문자 변환 | `"Hello".toUpperCase()` → `"HELLO"` |
| `trim()` | 앞뒤 공백 제거 | `" hello ".trim()` → `"hello"` |

### Collection 관련 메소드
| 메소드 | 설명 | 예시 |
|-------|------|------|
| `size()` | 컬렉션의 크기 반환 | `list.size()` |
| `add(E element)` | 요소 추가 | `list.add("item")` |
| `remove(Object o)` | 요소 제거 | `list.remove("item")` |
| `contains(Object o)` | 요소 포함 여부 확인 | `list.contains("item")` |
| `clear()` | 모든 요소 제거 | `list.clear()` |
| `isEmpty()` | 비어있는지 확인 | `list.isEmpty()` |
| `sort(Comparator<? super E> c)` | 정렬 | `list.sort(Comparator.naturalOrder())` |
| `stream()` | 스트림 변환 | `list.stream().filter(s -> s.length() > 3)` |

### 날짜 관련 메소드 (Java 8+)
| 메소드 | 설명 | 예시 |
|-------|------|------|
| `LocalDate.now()` | 현재 날짜 | `LocalDate.now()` |
| `LocalDateTime.now()` | 현재 날짜와 시간 | `LocalDateTime.now()` |
| `plusDays(long days)` | 날짜 더하기 | `date.plusDays(5)` |
| `minusMonths(long months)` | 날짜 빼기 | `date.minusMonths(1)` |
| `format(DateTimeFormatter formatter)` | 날짜 포맷팅 | `date.format(DateTimeFormatter.ofPattern("yyyy-MM-dd"))` |
| `parse(CharSequence text)` | 문자열을 날짜로 변환 | `LocalDate.parse("2025-04-23")` |

---

## JavaScript

### String 메소드
| 메소드 | 설명 | 예시 |
|-------|------|------|
| `length` | 문자열 길이 | `"hello".length` → `5` |
| `charAt(index)` | 특정 위치의 문자 반환 | `"hello".charAt(1)` → `'e'` |
| `substring(start, end)` | 부분 문자열 반환 | `"hello".substring(1, 3)` → `"el"` |
| `indexOf(substring)` | 문자열 위치 찾기 | `"hello".indexOf("el")` → `1` |
| `replace(search, replace)` | 문자열 치환 | `"hello".replace("l", "r")` → `"herlo"` |
| `split(separator)` | 문자열 분리 | `"h,e,l,l,o".split(",")` → `["h","e","l","l","o"]` |
| `toUpperCase()` / `toLowerCase()` | 대소문자 변환 | `"Hello".toUpperCase()` → `"HELLO"` |
| `trim()` | 앞뒤 공백 제거 | `" hello ".trim()` → `"hello"` |

### Array 메소드
| 메소드 | 설명 | 예시 |
|-------|------|------|
| `length` | 배열 길이 | `[1, 2, 3].length` → `3` |
| `push(element)` | 배열 끝에 요소 추가 | `array.push(4)` |
| `pop()` | 배열 마지막 요소 제거 및 반환 | `array.pop()` |
| `shift()` / `unshift(element)` | 배열 첫 요소 제거/추가 | `array.shift()`, `array.unshift(0)` |
| `slice(start, end)` | 배열 일부 추출 | `[1, 2, 3, 4].slice(1, 3)` → `[2, 3]` |
| `splice(start, deleteCount, ...items)` | 배열 내용 변경 | `array.splice(1, 1, 'a', 'b')` |
| `forEach(callback)` | 각 요소마다 함수 실행 | `array.forEach(item => console.log(item))` |
| `map(callback)` | 각 요소를 변환한 새 배열 반환 | `[1, 2, 3].map(x => x * 2)` → `[2, 4, 6]` |
| `filter(callback)` | 조건에 맞는 요소만 필터링 | `[1, 2, 3].filter(x => x > 1)` → `[2, 3]` |
| `reduce(callback, initialValue)` | 배열을 하나의 값으로 축소 | `[1, 2, 3].reduce((acc, curr) => acc + curr, 0)` → `6` |
| `find(callback)` | 조건에 맞는 첫 요소 찾기 | `[1, 2, 3].find(x => x > 1)` → `2` |
| `some(callback)` / `every(callback)` | 조건 만족 요소 존재/모든 요소 조건 만족 | `[1, 2, 3].some(x => x > 2)` → `true` |

---

## Python

### 문자열 메소드
| 메소드 | 설명 | 예시 |
|-------|------|------|
| `len(string)` | 문자열 길이 | `len("hello")` → `5` |
| `string[index]` | 특정 위치의 문자 | `"hello"[1]` → `'e'` |
| `string[start:end]` | 부분 문자열 | `"hello"[1:3]` → `"el"` |
| `string.find(substring)` | 문자열 위치 찾기 | `"hello".find("el")` → `1` |
| `string.replace(old, new)` | 문자열 치환 | `"hello".replace("l", "r")` → `"herro"` |
| `string.split(separator)` | 문자열 분리 | `"h,e,l,l,o".split(",")` → `['h','e','l','l','o']` |
| `string.upper()` / `string.lower()` | 대소문자 변환 | `"Hello".upper()` → `"HELLO"` |
| `string.strip()` | 앞뒤 공백 제거 | `" hello ".strip()` → `"hello"` |
| `"separator".join(iterable)` | 문자열 합치기 | `",".join(["a", "b", "c"])` → `"a,b,c"` |

### 리스트 메소드
| 메소드 | 설명 | 예시 |
|-------|------|------|
| `len(list)` | 리스트 길이 | `len([1, 2, 3])` → `3` |
| `list.append(element)` | 요소 추가 | `lst.append(4)` |
| `list.pop([index])` | 요소 제거 및 반환 | `lst.pop()` |
| `list.insert(index, element)` | 특정 위치에 요소 삽입 | `lst.insert(0, 'start')` |
| `list.remove(element)` | 첫 번째 일치 요소 제거 | `lst.remove(3)` |
| `list.sort()` | 리스트 정렬 | `lst.sort()` |
| `sorted(iterable)` | 정렬된 새 리스트 반환 | `sorted([3, 1, 2])` → `[1, 2, 3]` |
| `list.count(element)` | 요소 등장 횟수 | `[1, 2, 2, 3].count(2)` → `2` |
| `list.index(element)` | 요소의 인덱스 찾기 | `[1, 2, 3].index(2)` → `1` |

### 딕셔너리 메소드
| 메소드 | 설명 | 예시 |
|-------|------|------|
| `dict.keys()` | 키 목록 반환 | `d.keys()` |
| `dict.values()` | 값 목록 반환 | `d.values()` |
| `dict.items()` | (키, 값) 쌍 반환 | `d.items()` |
| `dict.get(key, default)` | 키에 대한 값 가져오기 | `d.get('key', 'default')` |
| `dict.update(other_dict)` | 딕셔너리 업데이트 | `d.update({'a': 1, 'b': 2})` |
| `dict.pop(key)` | 키 제거 및 값 반환 | `d.pop('key')` |

---

## Spring Framework

### Controller 어노테이션
| 어노테이션 | 설명 | 예시 |
|-----------|------|------|
| `@Controller` | MVC 컨트롤러 지정 | `@Controller public class HomeController {...}` |
| `@RestController` | REST API 컨트롤러 지정 | `@RestController public class ApiController {...}` |
| `@RequestMapping` | 요청 URL 매핑 | `@RequestMapping("/api/users")` |
| `@GetMapping` | GET 요청 매핑 | `@GetMapping("/{id}")` |
| `@PostMapping` | POST 요청 매핑 | `@PostMapping("/create")` |
| `@PutMapping` | PUT 요청 매핑 | `@PutMapping("/{id}")` |
| `@DeleteMapping` | DELETE 요청 매핑 | `@DeleteMapping("/{id}")` |
| `@PathVariable` | URL 경로 변수 바인딩 | `@PathVariable Long id` |
| `@RequestParam` | 요청 매개변수 바인딩 | `@RequestParam String name` |
| `@RequestBody` | 요청 본문 바인딩 | `@RequestBody UserDto user` |

### Service 및 Repository 어노테이션
| 어노테이션 | 설명 | 예시 |
|-----------|------|------|
| `@Service` | 서비스 레이어 컴포넌트 | `@Service public class UserService {...}` |
| `@Repository` | 데이터 접근 레이어 컴포넌트 | `@Repository public interface UserRepository {...}` |
| `@Autowired` | 의존성 자동 주입 | `@Autowired private UserRepository userRepository;` |
| `@Transactional` | 트랜잭션 관리 | `@Transactional public void updateUser(...)` |
| `@Qualifier` | 동일한 타입의 빈 구분 | `@Qualifier("userServiceImpl")` |

### JPA 관련 어노테이션
| 어노테이션 | 설명 | 예시 |
|-----------|------|------|
| `@Entity` | JPA 엔티티 클래스 지정 | `@Entity public class User {...}` |
| `@Table` | 테이블 매핑 | `@Table(name="users")` |
| `@Id` | 기본 키 지정 | `@Id private Long id;` |
| `@GeneratedValue` | 키 생성 전략 | `@GeneratedValue(strategy = GenerationType.IDENTITY)` |
| `@Column` | 컬럼 매핑 | `@Column(name="user_name", nullable=false)` |
| `@OneToMany` | 일대다 관계 | `@OneToMany(mappedBy = "user")` |
| `@ManyToOne` | 다대일 관계 | `@ManyToOne @JoinColumn(name = "user_id")` |
| `@ManyToMany` | 다대다 관계 | `@ManyToMany @JoinTable(name = "user_roles",...)` |

---

## SQL

### 기본 쿼리
| 쿼리 유형 | 구문 | 예시 |
|----------|------|------|
| SELECT | `SELECT columns FROM table WHERE condition` | `SELECT * FROM users WHERE age > 18` |
| INSERT | `INSERT INTO table (columns) VALUES (values)` | `INSERT INTO users (name, age) VALUES ('John', 25)` |
| UPDATE | `UPDATE table SET column = value WHERE condition` | `UPDATE users SET name = 'John' WHERE id = 1` |
| DELETE | `DELETE FROM table WHERE condition` | `DELETE FROM users WHERE id = 1` |
| JOIN | `SELECT * FROM table1 JOIN table2 ON condition` | `SELECT * FROM orders JOIN users ON orders.user_id = users.id` |

### 집계 함수
| 함수 | 설명 | 예시 |
|-----|------|------|
| COUNT() | 행 개수 반환 | `SELECT COUNT(*) FROM users` |
| SUM() | 합계 계산 | `SELECT SUM(amount) FROM orders` |
| AVG() | 평균 계산 | `SELECT AVG(age) FROM users` |
| MAX() / MIN() | 최대/최소값 | `SELECT MAX(price) FROM products` |
| GROUP BY | 그룹별 집계 | `SELECT category, COUNT(*) FROM products GROUP BY category` |

---

## 알고리즘 관련 메소드

### Java에서 자주 사용하는 알고리즘 메소드
| 메소드 | 설명 | 예시 |
|-------|------|------|
| `Arrays.sort(array)` | 배열 정렬 | `Arrays.sort(arr)` |
| `Collections.sort(list)` | 리스트 정렬 | `Collections.sort(list)` |
| `Math.max(a, b)` / `Math.min(a, b)` | 최대/최소값 | `Math.max(5, 10)` → `10` |
| `PriorityQueue<>()` | 우선순위 큐 | `PriorityQueue<Integer> pq = new PriorityQueue<>()` |
| `HashMap<K, V>()` | 해시맵 | `HashMap<String, Integer> map = new HashMap<>()` |

### Python에서 자주 사용하는 알고리즘 메소드
| 메소드 | 설명 | 예시 |
|-------|------|------|
| `sorted(iterable)` | 정렬된 배열 반환 | `sorted([3, 1, 2])` → `[1, 2, 3]` |
| `min(iterable)` / `max(iterable)` | 최소/최대값 | `min([1, 2, 3])` → `1` |
| `sum(iterable)` | 합계 계산 | `sum([1, 2, 3])` → `6` |
| `collections.deque()` | 양방향 큐 | `deque = collections.deque([1, 2, 3])` |
| `heapq` | 힙 큐 | `heapq.heappush(heap, item)` |
| `collections.Counter()` | 요소 등장 횟수 세기 | `Counter("hello")` → `{'h': 1, 'e': 1, 'l': 2, 'o': 1}` |

---

## 기타 유용한 메소드

### 정규 표현식
| 패턴 | 설명 | 예시 |
|-----|------|------|
| `^` | 문자열 시작 | `^hello` - "hello"로 시작하는 문자열 |
| `$` | 문자열 끝 | `world$` - "world"로 끝나는 문자열 |
| `.` | 임의의 한 문자 | `h.llo` - "hello", "hallo" 등과 일치 |
| `*` | 0회 이상 반복 | `a*b` - "b", "ab", "aab" 등과 일치 |
| `+` | 1회 이상 반복 | `a+b` - "ab", "aab" 등과 일치 |
| `?` | 0회 또는 1회 반복 | `a?b` - "b", "ab"와 일치 |
| `\d` | 숫자 | `\d{3}` - 3자리 숫자와 일치 |
| `\w` | 알파벳, 숫자, _ | `\w+` - 단어와 일치 |
| `[]` | 문자 클래스 | `[aeiou]` - 모음과 일치 |

### JSON 관련 메소드
| 언어 | 메소드 | 설명 | 예시 |
|-----|--------|------|------|
| Java (Jackson) | `objectMapper.writeValueAsString(obj)` | 객체를 JSON 문자열로 변환 | `objectMapper.writeValueAsString(user)` |
| Java (Jackson) | `objectMapper.readValue(json, Class)` | JSON 문자열을 객체로 변환 | `objectMapper.readValue(json, User.class)` |
| JavaScript | `JSON.stringify(obj)` | 객체를 JSON 문자열로 변환 | `JSON.stringify({name: "John"})` |
| JavaScript | `JSON.parse(string)` | JSON 문자열을 객체로 변환 | `JSON.parse('{"name":"John"}')` |
| Python | `json.dumps(obj)` | 객체를 JSON 문자열로 변환 | `json.dumps({"name": "John"})` |
| Python | `json.loads(string)` | JSON 문자열을 객체로 변환 | `json.loads('{"name": "John"}')` |

---

## 메소드 활용 예시

### Java 스트림 API 예시
```java
List<String> names = Arrays.asList("John", "Jane", "Adam", "Tom");

// 필터링 후 정렬
List<String> filteredNames = names.stream()
    .filter(name -> name.startsWith("J"))
    .sorted()
    .collect(Collectors.toList());
// 결과: ["Jane", "John"]

// 매핑 후 평균 계산
double average = names.stream()
    .mapToInt(String::length)
    .average()
    .orElse(0);
// 결과: 3.5
```

### Python 리스트 컴프리헨션 예시
```python
numbers = [1, 2, 3, 4, 5]

# 짝수만 필터링하고 제곱하기
squares = [x**2 for x in numbers if x % 2 == 0]
# 결과: [4, 16]

# 딕셔너리 컴프리헨션
name_lengths = {name: len(name) for name in ["John", "Jane", "Adam"]}
# 결과: {"John": 4, "Jane": 4, "Adam": 4}
```

### JavaScript 배열 메소드 체이닝 예시
```javascript
const people = [
  { name: "John", age: 25 },
  { name: "Jane", age: 30 },
  { name: "Adam", age: 20 }
];

// 20대 이름만 추출하여 대문자로 변환
const twentiesNames = people
  .filter(person => person.age >= 20 && person.age < 30)
  .map(person => person.name.toUpperCase());
// 결과: ["JOHN"]
```

---

## 메소드 추가 및 업데이트

이 문서는 계속해서 업데이트됩니다. 새로운 메소드나 함수를 배우게 되면 적절한 섹션에 추가하세요.

마지막 업데이트: 2025-04-23
