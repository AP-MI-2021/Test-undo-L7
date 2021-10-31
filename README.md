# Test pentru undo-redo laboratorul 7

Pentru a se accepta acest lab trebuie să demonstrați că operațiile de undo și redo se comportă corect pe scenariul de testare de mai jos. Acest scenariu ar trebui implementat și ca teste cu asserturi pentru undo și redo.

De asemenea, trebuie prezentate teste cu assert și pentru operațiunile care modifică mai multe entități: un singur undo va trebui să anuleze toate modificările cauzate de o astfel de operație.

| Nr. | Operațiune      | Lista de obiecte | Explicație |
| --- | --------------- | ---------------- | ---------- |
| 1   | start program   | []               | lista initiala goala |
| 2   | add o1          | [o1]             | adaugam un obiect |
| 3   | add o2          | [o1, o2]         | adaugam inca un obiect |
| 4   | add o3          | [o1, o2, o3]     | adaugam inca un obiect |
| 5   | undo            | [o1, o2]         | undo scoate ultimul obiect adaugat |
| 6   | undo            | [o1]             | inca un undo scoate penultimul obiect adaugat |
| 7   | undo            | []               | inca un undo scoate si primul element adaugat |
| 8   | undo            | []               | inca un undo nu face nimic |
| 9   | add o1, o2, o3  | [o1, o2, o3]     | adaugam trei obiecte |
| 10  | redo            | [o1, o2, o3]     | redo nu face nimic |
| 11  | undo, undo      | [o1]             | doua undo-uri scot ultimele 2 obiecte |
| 12  | redo            | [o1, o2]         | redo anuleaza ultimul undo, daca ultima operatie e undo |
| 13  | redo            | [o1, o2, o3]     | redo anuleaza si primul undo |
| 14  | undo, undo      | [o1]             | doua undo-uri scot ultimele 2 obiecte |
| 15  | add o4          | [o1, o4]         | adaugam un obiect |
| 16  | redo            | [o1, o4]         | redo nu face nimic, deoarece ultima operatie nu este un undo |
| 17  | undo            | [o1]             | undo anuleaza adaugarea lui o4 |
| 18  | undo            | []               | undo anuleaza adaugarea lui o1 - practic se continua sirul de undo de la pct 14 |
| 19  | redo, redo      | [o1, o4]         | se anuleaza ultimele 2 undo-uri |
| 20  | redo.           | [o1, o4]         | redo nu face nimic |
