# SWExpertAcademy_D3_Java_8741

## SW Expert Academy D4 8741. 두문자어

### 1. 문제설명

출처: https://swexpertacademy.com/main/code/problem/problemDetail.do?contestProbId=AW2y6n3qPXQDFATy&categoryId=AW2y6n3qPXQDFATy&categoryType=CODE

input으로 문자열이 들어온다. 공백으로 나눠진 단어의 앞글자를 각각 대문자로 바꾸어 이어붙인 문자열을 출력하는 문제.

[입력]

> 첫 번째 줄에 테스트 케이스의 수 `T`가 주어진다.
> 각 테스트 케이스의 첫 번째 줄에는 영어 소문자로 이루어진 세 문자열이 주어진다.
> 각 문자열의 길이는 `1`이상 `20`이하이다.

[출력]

> 각 테스트 케이스마다 `#x`(`x`는 테스트케이스 번호를 의미하며 `1`부터 시작한다)를 출력하고,
> 각 테스트 케이스 마다 입력으로 주어진 문자열의 앞글자를 대문자로 바꿔 순서대로 출력한다.

### 2. 풀이

코딩테스트 문제를 풀면서 가장 많이 사용하는 `StringTokenizer`와 `StringBuilder`를 이용하는 문제. 들어온 문자열을 공백으로 나누고 하나씩 가져와 첫번째 문자를 가져온다. 이 `Character`를 대문자로 바꾼 후 `StringBuilder`에 토큰이 더이상 없을 때 까지 붙여 결과를 출력하여 해결하였다. 

```java

	public static void main(String args[]) throws Exception
	{
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));
		
		int T = Integer.parseInt(br.readLine());

		for (int test_case = 1; test_case <= T; test_case++)
		{
			StringTokenizer st = new StringTokenizer(br.readLine());
			StringBuilder sb = new StringBuilder();

			while (st.hasMoreTokens())
				sb.append(Character.toUpperCase(st.nextToken().charAt(0)));
			
			bw.write("#"+test_case+" "+sb.toString()+"\n");
		}
		bw.flush();
		bw.close();
	}

```
