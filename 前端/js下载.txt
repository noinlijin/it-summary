
# chrome下可用的下载完成事件
  原因: chrome下面不会在iframe上面抛出load事件
  由客户端发送一个cookie的key,然后由服务器端发送这个cookie过来.客户端轮询判断这个cookie是否存在.如果存在表示下载完毕...
        	//显示动画
            Util.gif.open();
            $('#dialog .btn').hide();
	        var iframe=document.createElement('iframe');
	        iframe.style.display = "none";
	        //完成代码
	        var finish_code = 'finish_code_'+Math.random();
	        iframe.src=$(this).attr('target-href')+'&check_finish_code='+finish_code;
	        document.body.appendChild(iframe);
	        //轮询判断下载完毕
	        var timer = setInterval(function(){
	        	if (document.cookie.search(finish_code)<0){
	        		return;
	        	}
	        	clearInterval(timer);
	        	document.cookie = finish_code+'=; expires=Thu, 01 Jan 1970 00:00:00 GMT; path=/;';
	        	Util.gif.close();
	        	$('#dialog .btn').show();
	        },1000);