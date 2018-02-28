---
title: "Psaní kódu jazyka JavaScript | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.htmldesigner.html
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- code, JavaScript syntax
- comments, JavaScript code
- JavaScript code
ms.assetid: dde28266-0d0f-4460-a819-f931cf0911ad
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e50bc25f818724b59d9adda51f97d76ae14de2b4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="writing-javascript-code"></a>Psaní kódu jazyka JavaScript
Jako mnoho jinými programovací jazyky [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] je uspořádán do příkazy, který se skládá z související sady příkazů a komentáře bloky. V rámci příkazu můžete proměnné, řetězců, čísel a výrazy.  
  
## <a name="statements"></a>Příkazy  
 A [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] programu je kolekce příkazy. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]příkazy kombinovat výrazy tak, že provádějí dokončení úloh.  
  
 Příkaz se skládá z jedné nebo více výrazů, klíčová slova nebo operátory (symbolů). Příkaz je obvykle zapisují na jeden řádek, i když příkaz může být napsán přes dvě nebo více řádků. Dvě či více příkazech také může být napsán na stejném řádku jejich oddělením středníkem. Obecně platí každého nového řádku začne nové prohlášení. Je vhodné explicitně ukončení příkazů. Můžete to provést pomocí středník (;), který je [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] znaků ukončení příkazu.  
  
 Zde jsou dva příklady [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] příkazy. Věty po / / znaky jsou *komentáře*, které jsou vysvětlující poznámky v programu.  
  
```JavaScript  
var aBird = "Robin"; // Assign the text "Robin" to the variable aBird.  
var today = new Date(); // Assign today's date to the variable today.  
```  
  
 Skupina [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] příkazy v závorkách ({}) se nazývá *bloku*. Příkazy, které jsou seskupeny do bloku lze obecně zacházet jako jediný příkaz. To znamená, že používáte bloky většinu umístí [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] očekává jeden příkaz. Mezi významné výjimky patří hlavičky **pro** a `while` smyčky. Všimněte si, že jeden příkazy v bloku končit středníkem, ale nemá samotného bloku.  
  
 Bloky se obecně používají ve funkcích a podmíněné příkazy. Všimněte si, že na rozdíl od C++ a některé další jazyky, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] nemá nebere v úvahu blok jako nový obor; pouze funkce vytvoření nového oboru.  
  
 V následujícím příkladu `else` klauzule WHERE obsahuje blok dvou příkazů v závorkách. Blok je zpracovaná jako jediný příkaz. Také funkce samotné se skládá z blok příkazů v závorkách. Příkazy následující funkce jsou mimo blok a nejsou proto součástí v definici funkce.  
  
```JavaScript  
function inchestometers(inches)  
   {  
   if (inches < 0)  
      return -1;  
   else  
      {  
      var meters = inches / 39.37;  
      return meters;  
      }  
   }  
  
var inches = 12;  
var meters = inchestometers(inches);  
document.write("the value in meters is " + meters);  
```  
  
## <a name="comments"></a>Komentáře  
 Jeden řádek [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] komentář začíná pár lomítka (/ /). Tady je příklad komentáře jeden řádek.  
  
```JavaScript  
var aGoodIdea = "Comment your code thoroughly."; // This is a single-line comment.  
```  
  
 Víceřádkový [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] komentář začíná hvězdičkou a lomítkem (/ *) a končí zpětného (\*/).  
  
```JavaScript  
/*  
This is a multiline comment that explains the preceding code statement.  
  
The statement assigns a value to the aGoodIdea variable. The value,   
which is contained between the quote marks, is called a literal. A   
literal explicitly and directly contains information; it does not   
refer to the information indirectly. The quote marks are not part   
of the literal.  
*/  
```  
  
> [!NOTE]
>  Pokud se pokusíte vložit jeden víceřádkových komentářů v rámci druhého, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] interpretuje výsledné Víceřádkový komentář neočekávaným způsobem. * / Který označuje konec vložený Víceřádkový komentář interpretována jako konec celý Víceřádkový komentář. To znamená, že text, který následuje embedded Víceřádkový komentář nesmí být označené jako komentář; Místo toho bude vyhodnocen jako [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] kód a vygeneruje chyby syntaxe.  
  
 Doporučuje se zapsat všechny komentáře jako bloky jeden řádek komentáře. To umožňuje komentář velké segmenty kódu pomocí víceřádkovým komentář později.  
  
```JavaScript  
// This is another multiline comment, written as a series of single-line comments.  
// After the statement is executed, you can refer to the content of the   
// aGoodIdea variable by using its name.  
var extendedIdea = aGoodIdea + " You never know when you'll have to figure out what it does.";  
```  
  
## <a name="assignments-and-equality"></a>Přiřazení a rovnosti  
 Rovná se (=) se používá v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] příkazy přiřadit hodnoty proměnných: je operátor přiřazení. Operand vlevo = operátor je vždy Lvalue. Příkladem hodnoty lvalue jsou:  
  
-   proměnné,  
  
-   elementy pole  
  
-   vlastnosti objektu.  
  
 Pravý operand = operátor je vždy Rvalue. Rvalue může být libovolný hodnotu libovolného typu, včetně hodnot výrazu. Tady je příklad [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] příkaz přiřazení.  
  
```JavaScript  
var anInteger = 3;  
```  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] Kompilátor interpretuje jako význam tento příkaz: "proměnné přiřadit hodnotu 3 **anInteger**," nebo "**anInteger** načítá hodnotu 3."  
  
 Ujistěte se, pochopit rozdíl mezi = – operátor (přiřazení) a == – operátor (rovnosti). Když chcete k porovnání dvou hodnot a zjistěte, jestli jsou stejné, použijte dva symboly rovná se (==). To je podrobněji v [řízení toku programu](../javascript/controlling-program-flow-javascript.md).  
  
## <a name="expressions"></a>Výrazy  
 A [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] hodnota výrazu může být libovolný platný [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] typu – číslo, řetězec, k objektu a tak dále. Nejjednodušší výrazy jsou literály. Tady jsou některé příklady [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] literálu výrazy.  
  
```JavaScript  
3.9                       // numeric literal  
"Hello!"                  // string literal  
false                     // boolean literal  
null                      // literal null value  
{x:1, y:2}                // Object literal  
[1,2,3]                   // Array literal  
function(x){return x*x;}  // function literal  
```  
  
 Složitější výrazy může obsahovat proměnné, volání funkcí a dalších výrazů. Můžete kombinovat výrazy k vytvoření složitých výrazů pomocí operátorů. Příklady operátory: `+` (navíc) `-` (odčítání), `*` (násobení), a `/` (division).  
  
 Tady jsou některé příklady [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] složité výrazy.  
  
```JavaScript  
var anExpression = 3 * (4 / 5) + 6;  
var aSecondExpression = Math.PI * radius * radius;  
var aThirdExpression = aSecondExpression + "%" + anExpression;  
var aFourthExpression = "(" + aSecondExpression + ") % (" + anExpression + ")";  
```