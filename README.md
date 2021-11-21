# umimecesky-solver

function solve() {
  document.getElementById("cards").innerHTML += "<div id='cardss'></div>"
   try {
      var odpovedi = questions.find(q => q.id == window.location.pathname.split("/")[2])
      var explanation = odpovedi.options.find(o => o.correct === 1)
      var odpoved = explanation.option[0][1]
      document.getElementById("cardss").innerHTML = `<p style="font-size:34px;">Odpověd: ${odpoved}</p>`
      console.log("Odpověd je: <"+odpoved+">")
   } catch (error) {}
}
solve()
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Lepší verze
var odpovedi = questions.find(q => q.id == window.location.pathname.split("/")[2])
var explanation = odpovedi.options.find(o => o.correct === 1)
var odpoved = explanation.option[0][1]
$("span:contains("+odpoved+")").click()
console.log("Odpověd je: <"+odpoved+">")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
100% funguje
var odpovedi = questions.find(q => q.id == window.location.pathname.split("/")[2])
var explanation = odpovedi.options.find(o => o.correct === 1)
console.log("Odpověd je: <"+explanation.option[0][1]+">")
