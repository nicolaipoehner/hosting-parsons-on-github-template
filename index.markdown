<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "void breitensucheStarten(int start) {
\n" +
    "    besucht[start] = true;
\n" +
    "    warteschlange[0] = start;
\n" +
    "    int wartePos=1; 
\n" +
    "    int besKnoten=0;
\n" +
    "    while(wartePos != 0) {
\n" +
    "        int aktuellerKn = warteschlange[0];
\n" +
    "        entfernen(warteschlange);
\n" +
    "        wartePos--;
\n" +
    "        reihenfolge[besKnoten] = aktuellerKn;
\n" +
    "        besKnoten++;
\n" +
    "        for(int i = 0; i &lt; anzahlKnoten; i++) {
\n" +
    "            if(adjazenzmatrix[aktuellerKn][i] &gt; 0 &amp;&amp; besucht[i] == false) {
\n" +
    "                besucht[i] = true;
\n" +
    "                warteschlange[wartePos] = i;
\n" +
    "                wartePos++;
\n" +
    "            }
\n" +
    "        }
\n" +
    "    }
\n" +
    "    reihenfolgeAusgeben();
\n" +
    "}";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
