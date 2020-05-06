網頁外鏈用了target=_blank 實作釣魚網站 [駭客/黑客 簡易實測防堵] (Easy Html Hacker)


資料來源: https://mp.weixin.qq.com/s?__biz=MzAwNDcyNjI3OA==&mid=2650843730&idx=1&sn=7448e0970333804e2c5ce64d232a9c30&chksm=80d3813bb7a4082dc241c969fb0352ec060ee1849b6dc230df1703360829c7a2a9b4bbdc53ed&scene=126&sessionid=1588733402&key=9478b17497cce279bd5645f418bd67cb347c98bab3b2edaef4386c7998a7ed1a280bb97d2a67c1b761b9ff01b051b05d665df4205b36fbba356ae3c1f1513dc7403cebcbb7b424b6a60b9c0a23086747&ascene=1&uin=MjIwODk2NDgxNw%3D%3D&devicetype=Windows+10+x64&version=62090070&lang=zh_TW&exportkey=ArcjTOdbb%2FbxbcAQH9IpptQ%3D&pass_ticket=qXeqndIrTf6UDYCQB%2FFtSDnDrJUw2fDiC70IP1OM78LgY%2Bs5XQ6qFbersqWcDyHR


如果只是加上target="_blank"，打開新窗口後，新頁面能通過window.opener獲取到來源頁面的window對象，即使跨域也一樣。雖然跨域的頁面對於這個對象的屬性訪問有所限制，但還是有漏網之魚。

這是某網頁打開新窗口的頁面控制台輸出結果。可以看到window.opener的一些屬性，某些屬性的訪問被攔截，是因為跨域安全策略的限制。

即便如此，還是給一些操作留下可乘之機。比如修改window.opener.location的值，指向另外一個地址。你想想看，剛剛還是在某個網站瀏覽，隨後打開了新窗口，結果這個新窗口神不知鬼不覺地把原來的網頁地址改了。這個可以用來做什麼？釣魚啊！等你回到那個釣魚頁面，已經偽裝成登錄頁，你可能就稀里糊塗把賬號密碼輸進去了。

