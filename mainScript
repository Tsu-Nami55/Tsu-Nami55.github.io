window.onload = async function() {
    var buttonID;
    document.getElementById("citMjrButton").onclick = function() {
        buttonID = "CIT";
        getData(buttonID);
    }
    document.getElementById("busMjrButton").onclick = function() {
        buttonID = "BUS";
        getData(buttonID);
    }
}

async function getData(ID) {
    var url = "cit5students.json";
    var response = await fetch(url);
    if (response.ok) {
      
        var data = await response.json();

        if (ID == "CIT") {
            var filter = data.filter((data) => data.major == "CIT");
        }
        else if (ID == "BUS") {
            var filter = data.filter((data) => data.major == "BUS");
        }
            
        var tblTemp = document.getElementById("tableTemplate").innerHTML;
        var compTblTemp = Handlebars.compile(tblTemp);
        compHtml = compTblTemp({rows: filter})
        document.getElementById('mjrTable').innerHTML = compHtml;
    }
    else {
        document.querySelector('#mjrTable').innerHTML = "Data not found.";
    }
}
