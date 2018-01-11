# Microsoft REST API 가이드라인에 기여하기
Microsoft REST API 가이드라인은 Microsoft 주도의 REST APIs를 위한 개발자들에게 일관적인 디자인 정책입니다. 이 정책은 Microsoft 내외의 다양한 개인들의 피드백과 입력을 필요로 합니다.

피드백을 제공하기 위해서는 이 문서에 있는 가이드를 준수하여 주십시오. 단, 가이드는 가이드 일뿐, 규정이 아닙니다. 당신이 판단하시기에 기여 가이드라인을 포함하여 이 저장소에 있는 그 어떠한 것들이라도 가장 적합하다고 생각하시는 것들을 자유롭게 제안하여 주십시오.

이 프로젝트는 [Contributor Code of Conduct][code-of-conduct]로 배포됩니다. 이 프로젝트에 참여함으로서 당신은 이러한 조건들을 준수하는것에 동의한 것으로 간주됩니다. 
- [이슈 등록](#이슈-등록)
- [문서 스타일 가이드](#문서-스타일-가이드)
- [커밋 메세지](#커밋-메세지)
- [풀 리퀘스트](#풀-리퀘스트)

## 이슈 등록
- 당신은 [create an issue][new-issue]를 하실 수 있습니다. 그러나 하시기 전에 아래 내용을 먼저 읽고 그 내용을 최대한 자세히 포함시켜 주십시오.
- [cursory search][issue-search]을 실행하여 이슈 등록 전비슷한 이슈가 있는지 확인하여 주십시오.
- 당신이 사용하는 Microsoft REST API 가이드라인의 버전을 알려주십시오.
- 당신이 원하시는 방식의 다른 곳에서 발견한 가이드라인을 포함시켜 주십시오. 예) [백악관 웹 API 규정(영어)][white-house-api-guidelines].
- 가능한 반드시 예시 리퀘스트와 레스폰스를 포함시켜 주십시오.

### 관련 저장소.
이 저장소는 [Microsoft REST API Guidelines](https://github.com/Microsoft/api-guidelines) 문서 Only 입니다. 저장소에 맞는 ISSUE를 등록하시는지 확인하여 주십시오.

## 기여를 위한 추천 설정
- [Atom][atom], [VS Code][vscode] 등 즐겨쓰는 에디터를 설치해 주십시오.
- [markdown-toc package][markdown-toc]를 설치해 주십시오.

## 문서 스타일 가이드
- [GitHub-flavored markdown][gfm]를 사용해 주십시오.
- 자유롭게 예제의 강조문법을 사용해주십시오. 
- HTTP requests의 공백라인은 삭제하여 주십시오.
- 예제를 이해할수 있는 필수적인 헤더만 유지하여 주십시오.
- 멤버 이름, 따옴표 등 2 Space 인덴트를 사용하여 유요한 pretty-printed JSON를 사용하여 주십시오. 
- JSON payloads는 축소기능을 사용하여 최소화 하여 주십시오.
- 한 문장에 한 라인만 써 주십시오.

### 예제
#### Request

```http
GET http://services.odata.org/V4/TripPinServiceRW/People HTTP/1.1
Accept: application/json
```

#### Response

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@nextLink":"http://services.odata.org/V4/TripPinServiceRW/People?$skiptoken=8",
  "value":[
    {
      "userName":"russellwhyte",
      "firstName":"Russell",
      "lastName":"Whyte",
      "emails":[
        "Russell@example.com",
        "Russell@contoso.com"
      ],
      "addressInfo":[
        {
          "address":"187 Suffolk Ln.",
          "city":{
            "countryRegion":"United States",
            "name":"Boise",
            "region":"ID"
          }
        }
      ],
      "gender":"Male",
    },
    ...
  ]
}
```

## 커밋 메세지
- 현재 시제를 사용해 주십시오 : "Change ...", not "Changed ..."
- 명령법을 사용해 주십시오 : "Change ...", not "Changes ..."
- 첫라인은 72자 이하로 제한합니다.
- 자유롭게 이슈와 풀 리퀘스트를 레퍼런스해 주십시오.

## 풀 리퀘스트
풀 리퀘스트는 제안과 채택(accepted)으로 기여의 주요한 메커니즘을 담당합니다. 우리는 [topic branch][topic-branch]를 만들고 그것으로부터 `master` 브렌치에 풀 리퀘스트를 전송하는 것을 추천합니다. 추가적인 가이드라인은 [GitHub Flow Guide][github-flow-guide]을 확인하여 주십시오.

필요하다면 당신의 풀리퀘스트와 피드백을 반복할 준비가 되어 있습니다.

[code-of-conduct]: https://opensource.microsoft.com/codeofconduct/
[new-issue]: https://github.com/Microsoft/api-guidelines/issues/new
[issue-search]: https://github.com/Microsoft/api-guidelines/issues
[white-house-api-guidelines]: https://github.com/WhiteHouse/api-standards/blob/master/README.md
[topic-branch]: http://www.git-scm.com/book/en/v2/Git-Branching-Branching-Workflows#Topic-Branches
[gfm]: https://guides.github.com/features/mastering-markdown/#GitHub-flavored-markdown
[github-flow-guide]: https://guides.github.com/introduction/flow/
[atom-beautify]: https://atom.io/packages/atom-beautify
[atom]: http://atom.io
[markdown-toc]: https://atom.io/packages/markdown-toc
[vscode]: https://code.visualstudio.com/
