<!DOCTYPE html>
<meta charset="UTF-8">
<html><body>
    <title>中間検査システム</title>
    <div><em><font size ="6" color =#4169e1>中間検査システム</font></em></div><br>
    <hr></hr>
    <p>　作業日　　　 　: <input size =10 type="text" name= "textDay"value=""></p>
    <p>　製造指図No　: <input maxlength=12 type="text" name= "textSASIZU"value="">
        　受注No　　: <input type="text" name= "textJYUTYUNO"value=""></p>
    <p>　製品CD 　　　: <input type="text" name= "textSEIHINCD"value="">
        　配合名　　　: <input type="text" name= "textHAIGOUNAME"value=""></p>
    <p>　製品名 　　　　: <input size =60 type="text" name= "textSEIHINNAME"value=""></p>

    <p>成形機<select name="example">
        <option value="選択肢1">5号P</option>
        <option value="選択肢2">6号P</option>
        <option value="選択肢3">7号P</option>
        </select></p><br>
        <input />
    <p>　　　　[測定値]　　　[寸法規格]　　　[焼成寸法]</p>
    <p>寸法１<input type="text" size =2 name= "textSUNPOU1SUNPOU1">
        　　　　<input type="text" size =2 name= "textSUNPOUKIKAKU1">
        　　　　　<input type="text" size =2 name= "textSYOUSEISUNPOU1"></p><br>    
    <br>
    <script>
        function update (_v)//input tagを更新する関数
        {
            document.querySelector( 'input' ).value=_v
        }

        function append(_v)//数字ボタンが押されたので数字を後ろに追加する
        {
            document.querySelector( 'input' ).value +=_v
        }

        function  calc()//「＝」が押されたので計算する
        {
            const v = document.querySelector( 'input' ).value
            const f = new Function( 'return ' + v )
            update( f().toString() )
        }
        
        </script>
        <p></p><button onclick="append('1')">1</button>
        <button onclick="append('2')">2</button>
        <button onclick="append('3')">3</button>
        <button onclick="append('+')">+</button></p>
        <p><button onclick="append('4')">4</button>
        <button onclick="append('5')">5</button>
        <button onclick="append('6')">6</button>
        <button onclick="append('-')">-</button></p>
        <p><button onclick="append('7')">7</button>
        <button onclick="append('8')">8</button>
        <button onclick="append('9')">9</button>
        <button onclick="append('=')">-</button></p>
        <p><button onclick="append('0')">0</button>
        <button size = 20 onclick="update('')">ＣＬＥＡＲ　</button></p><br>
        
            <form method="post" action="example.cgi">

            <p>作業者CD：<input type="text" name="textSAGYOUSYACD"></p>
            <p>作業者名  ：<input type="text" name="textSAGYOUSYANAME"></p>
            <p><input type="submit" value="測定完了"></p>
            </form>
            <hr></hr>
</body></html>
