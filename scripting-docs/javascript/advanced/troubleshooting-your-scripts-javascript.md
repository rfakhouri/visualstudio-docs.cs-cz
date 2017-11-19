---
title: "Řešení potíží se skripty (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- automative type conversion
- troubleshooting scripts
ms.assetid: 0e0545d9-44e5-4179-befc-99a882c5c672
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7e0193e6dc0996d5e2d0d3df7103c7705d29477
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="troubleshooting-your-scripts-javascript"></a>Řešení potíží se skripty (JavaScript)
Existují místech žádný programovací jazyk, které mají výskyt nečekaných událostí. Například `null` hodnotu [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] není chovají stejně jako `Null` hodnotu v jazycích C nebo C++.  
  
 Zde jsou některé oblasti řešení problémů, které vám může dojít při psaní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skripty.  
  
## <a name="syntax-errors"></a>Chyby syntaxe  
 Je důležité věnovat pozornost podrobností při psaní skriptů. Například řetězce musí být uzavřena v uvozovkách.  
  
## <a name="order-of-script-interpretation"></a>Pořadí interpretace skriptu  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]Interpretace je součástí analýze proces HTML webového prohlížeče. Zadáte-li skript dovnitř \<HEAD > značky v dokumentu, interpretuje se to před libovolná součást \<textu > značky. Pokud máte objekty, které jsou vytvořeny ve \<textu > značky, neexistují v době \<HEAD > je právě analyzovat a nelze upravovat skriptem.  
  
> [!NOTE]
>  Toto chování je specifické pro aplikaci Internet Explorer. Rozhraní ASP a prostředí WSH jsou různé provádění modely (stejně jako jiní hostitelé).  
  
## <a name="automatic-type-coercion"></a>Převod automatické typu  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]je jazyk volného typu s automatické převod. I když hodnoty s různé typy nejsou stejné, vyhodnocení výrazů v následujícím příkladu **true**.  
  
```JavaScript  
"100" == 100;  
false == 0;  
```  
  
 Chcete-li zkontrolovat, že typu a hodnoty jsou stejné, použijte operátor striktní rovnosti (=). Následující obou vyhodnotit na hodnotu false:  
  
```JavaScript  
"100" === 100;  
false === 0;  
```  
  
## <a name="operator-precedence"></a>Priorita operátorů  
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md) Určuje, kdy se provádí operace během vyhodnocování výrazu. V následujícím příkladu se provádí násobení před odčítání, i když odčítání jako první se objeví ve výrazu.  
  
```JavaScript  
theRadius = aPerimeterPoint - theCenterpoint * theCorrectionFactor;  
```  
  
## <a name="using-forin-loops-with-objects"></a>Pomocí for... v smyčky s objekty  
 Při procházení vlastností objektu s [for... v](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) smyčky, nedokáže předvídat a řídit pořadí, ve kterém jsou přiřazeny pole objektu k proměnné čítač smyčky. Kromě toho může být pořadí jiný v různých implementacích jazyka.  
  
## <a name="with-keyword"></a>with – klíčové slovo  
 [s](../../javascript/reference/with-statement-javascript.md) příkaz je vhodné pro přístup k vlastnosti, které již existují v zadaný objekt, ale nelze použít k přidání vlastnosti do objektu. Pokud chcete vytvořit nové vlastnosti v objektu, musí odkazovat na objekt konkrétně.  
  
## <a name="this-keyword"></a>This – klíčové slovo  
 I když používáte `this` – klíčové slovo v definici objektu najdete odkaz sám na sebe, nemůžete použít `this` nebo podobné klíčová slova k odkazování na aktuálně spuštěných funkce při této funkce není definici objektu. Pokud je pro přiřazení k objektu jako metodu, můžete použít `this` – klíčové slovo v rámci funkce odkazovat na objekt.  
  
## <a name="writing-a-script-that-writes-a-script-in-internet-explorer"></a>Zápis skript, který zapíše skript v aplikaci Internet Explorer  
 \< /SCRIPT > Značka aktuální skript ukončí, pokud překladač zaznamená ho. Chcete-li zobrazit "\</SCRIPT >" samostatně, přepište to jako aspoň dva řetězce, například "\</SCR" a "IPT >", který lze potom zřetězit společně v příkazu, který zapíše se.  
  
## <a name="implicit-window-references-in-internet-explorer"></a>Implicitní okno odkazy v aplikaci Internet Explorer  
 Vzhledem k tomu, že více než jeden interval může být najednou otevřený, všechny odkazy implicitní okno odkazuje na aktuální okno. Pro ostatní windows musíte použít explicitní odkaz.