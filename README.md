# ch05_html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>날짜 객체</title>
    <script>
        //코어객체 중 Date
        let now = new Date(); //현재시간
        console.log('now:',now);
        document.write('getDate:',now.getDate() + "<br>");
        // month는 0부터 시작
        document.write("getMonth:" + (now.getMonth() +1 ) + "<br>");
        document.write("getFullYear:" + now.getFullYear() + "<br>");
        //UTC(coordinated Universal Time) 전세계 사건 표준화를 위한 기준시간
        //1970년 1월 1일 00:00:00 UTC부터 현재까지의 밀리초를 출력
        document.write("getTime:" + now.getTime() + "<br>");
        document.write("toString():" + now.toString() + "<br>");
        document.write("now:" + now + "<br>");
        document.write("toUTCString():" +now.toUTCString() + "<br>");
        alert("기다리고 있음.");
        let after = new Date();
        document.write("접속 후"+
              ((after.getTime() - now.getTime()) / 1000 + "초 지남"));

    </script>
</head>
<body>
    
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>array</title>
</head>
<body>
    <h3>[] 로 배열 만들기</h3>
    <hr>
    <script>
        //let plots = [50, 5, 8, 15, 20];
        let plots = new Array [50, 5, 8, 15, 20]; //위와 동일함.
        console.log(plots[0]); //index으로 value에 접근
        console.log(typeof(plots)); 
        console.log(plots.length);
        plots.push(100) // 추가
        console.log(plots); 
        //1.for문
        for(let i=0; i< plots.length; i++){
            let size = plots[i];
            while(size > 0){
                document.write("*");
                size--;
            }
            document.write(plots[i]+"<br>");
        }
        //2. for in 문
        for(let i in plots){
            console.log(i + ":번째="+plots[i]);
        }
        //3. for of 문(value만 필요할때)
        for(let v of plots){
            console.log(v);
        }

    </script>
    
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>점심메뉴 추천기</title>
</head>
<body>
    <h3>선택을 도와드립니다.!!!</h3>
    <button type="button" id="btn" onclick="fn_select()">선택!</button>
    <div id = "view"></div>
    <hr>
    <script>
        let menu = ["정밀품", "묵은정", "짬뽕지존", "춘리마라탕", "매일돼지","다이어트", "귀리쉐이크", "맥날", "편의점"];
        function fn_select(){
            let random_num = Math.floor(Math.random() * menu.length);
            console.log(random_num);
            //1. random_num을 이용해서 div에 innerHTML에 메뉴를 출력하시오
            //2. button의 innerHTML의 '선택!'을 '다시선택!' 로 바꾸시오.
            document.getElementById("view").innerHTML = "<h1>오늘의 점심은'"+menu[random_num]+"'입니다. </h1>";
            document.getElementById("btn").innerHTML = "다시선택!";
            
            
        }
    </script>
    
    
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>메소드</title>
</head>
<body>
    <h3>Array method</h3>
    <hr>
    <script>
        let a = ["황김","황이","김", "이"];
        let b = new Array ("최", "박"); // 선언 및 초기화 (위와 같음)
        //concat 배열결합
        let c = a.concat(b);
        console.log("c:",c);
        //join 배열을 문자열고(구분자를 넣어서)
        let d = c.join("|");
        console.log("d=",d);
        //revers 좌우 반전
        console.log("reverse:",c.reverse());
        // pop (마지막 요소삭제)
        c.pop();
        console.log("c:",c);
        let shift = c.shift(); //처음요소 꺼내오고 배열에는 처음요소가 없어짐
        console.log("c(shift):",c);
        console.log("shift:",shift);
        c.unshift("선우") // 처음 요소에 삽입
        c.push("나") // 마지막 요소에 삽입
        console.log("push:",c);
        //slice 배열가져오기
        let first = c.slice(1,3) //1번쨰 인덱스에서 3-1인덱스까지 가져오기
        console.log(first);
        console.log(c);



        </script>
    
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>String</title>
</head>
<body>
    <h3>String method</h3>
    <hr>
    <script>
        let a = "Boys and Girls"
        //concat == 문자열+문자열
        console.log(a.concat("입니다"));
        //inedxOf
        console.log("indexOf:, a .indexOf"("s"));
        console.log("indexOf:, a .indexOf"("S")); //없으면 -1
        //slice 인덱으로 가져오기
        console.log('slice:',a.slice(5,8));
        //substr 시작인덱스 부터 길이
        console.log('substr:',a.substr(5,3));
        let sub = a.split("");// 구분자로 잘라서 배열에 담음
        console.log(sub);
        //replace 바꾸기
        console.log(a.replace("and","or"));
        //upper or lower
        console.log(a.toUpperCase());
        console.log(a.toLowerCase());

    </script>
    
</body>
</html>
