---
title: "Rnn"
draft: true
---

<button id="myButton">generate</button>
#  {textlist}
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script>
    $('#myButton').click(function() {
        $("div.loader").show();
        $.ajax({
            type:'POST',
            url: "/generate",
            dataType:"html",
            success: function(response){
                //console.log(response)
                var data = response.split("\n");
                //console.log(data)
                var list_html = "<ul style='list-style: none;'>";
                for( var i=0; i <data.length; i++) {
                   list_html += "<li>" + data[i] + "</li>";
                }
                list_html += "</ul>"
                $("div.loader").hide();
                $("#textlist").html(list_html);
            }
    });
    });
</script>