# fullstack app deployed to vercel

## frontend
### React + TypeScript + Vite

실제 화면에 보이는 정보로 client 폴더에 작성

## backend
### node + express

vercel 에서 node 서버가 실행되는 기본 방식은 api 폴더 내 index.ts 와 root 폴더의 vercel.json 정보가 필요하다. <br />
공식문서 참조 https://vercel.com/guides/using-express-with-vercel

## 테스트 환경

### window 11
vercel CLI의 vercel dev로 테스트는 어려운 것으로 보인다 <br />
(deploy시 정상적으로 실행되지만, vercel dev로 로컬 테스트시 cannot use import statement outside a module 오류 발생) <br />
따라서, npm run local-build 실행 후, npm run dev를 실행하여 로컬 환경 테스트를 할 수 있다.

## deploy 과정 및 예시

frontend는 root 폴더의 json의 build 정보를 참고하여 client폴더의 build 과정을 거친 후 완성된 build 파일(dist 폴더)를 root 페이지로 이동시킨다. <br />
backend는 vercel은 deploy 시 ts 파일을 인식하기에 별도의 컴파일 과정을 진행할 필요는 없기에 별도의 build 과정은 없다. <br />
<br />
deploy setting 값 중 OutPut Directory 값을 dist로 변경해야한다. <br />
sample vercel link: https://vercel-fullstack-gamma.vercel.app/


### 참조
공식 문서와 몇몇 사이트를 참고하여 완성하였으며, backend와 frontend를 분리하여 deploy하는 방식이 아닌<br />
하나의 app으로 작동할 수 있도록 설정하였다. <br />
#### 사이트 목록
https://vercel.com/guides/using-express-with-vercel <br />
https://www.grahamquan.com/posts/deploy-express-ts-to-vercel <br />
https://dev.to/tirthpatel/deploy-node-ts-express-typescript-on-vercel-284h <br />
