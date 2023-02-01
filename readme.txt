$json=array();
while ($row = mysqli_fetch_assoc($result)) {
            array_push($json,$row);
}

 echo json_encode($json);




-----------------------------------------------------------------------
------------------------------------------------------------------------




$.ajax({
method: "POST",
url: "response1.php",
data: {
section_id: section_id , day: day,facultyid: facultyid
},
//datatype: "html",
dataType: 'json',
success: function(data) {


//var jdata=JSON.parse(data);
var jdata=JSON.stringify(data);
jdata=JSON.parse(jdata);
//alert(jdata[0].from_time);
																
for(i in jdata){
																	
$("#fromtimeid").append("<option>"+jdata[i].from_time+"</option>");
$("#totimeid").append("<option>"+jdata[i].to_time+"</option>");
}





//$("#fromtimeid").html(data);
//alert(data[0].from_time);
// $("#fromtimeid").html(data.from_time);


}
});