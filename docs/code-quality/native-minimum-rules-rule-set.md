---
title: "Sady pravidel nativní minimální pravidla | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d898bc4-fba5-472e-8f09-b0c6b511c5a3
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6db3e112f45200221eff80c033daed4a04c152d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="native-minimum-rules-rule-set"></a>Sada pravidel Nativní minimální pravidla
Microsoft nativní minimální pravidla se zaměřit na nejdůležitější problémy v nativním kódu, včetně potenciální bezpečnostní díry a dojde k chybě aplikace. Toto pravidlo nastavit v žádné sadě vlastní pravidlo, že které vytvoříte pro nativní projekty by měla obsahovat.  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[C6001](../code-quality/c6001.md)|Pomocí neinicializované paměti|  
|[C6011](../code-quality/c6011.md)|Vyhodnocení ukazatele Null.|  
|[C6029](../code-quality/c6029.md)|Nezaškrtnuté hodnota|  
|[C6053](../code-quality/c6053.md)|Nulové ukončení z volání|  
|[C6059](../code-quality/c6059.md)|Chybný zřetězení|  
|[C6063](../code-quality/c6063.md)|Chybí Argument řetězce k formátování – funkce|  
|[C6064](../code-quality/c6064.md)|Chybí Argument celé číslo k formátování – funkce|  
|[C6066](../code-quality/c6066.md)|Chybí Argument ukazatele k formátování – funkce|  
|[C6067](../code-quality/c6067.md)|Chybí Argument řetězce ukazatele k formátování – funkce|  
|[C6101](../code-quality/c6101.md)|Vrácení neinicializované paměti|  
|[C6200](../code-quality/c6200.md)|Index překračuje maximální vyrovnávací paměti|  
|[C6201](../code-quality/c6201.md)|Index překračuje maximální zásobníku vyrovnávací paměti|  
|[C6270](../code-quality/c6270.md)|Chybí Argument Float k formátování – funkce|  
|[C6271](../code-quality/c6271.md)|Nadbytečný Argument k formátování – funkce|  
|[C6272](../code-quality/c6272.md)|Argument typu Float k formátování – funkce|  
|[C6273](../code-quality/c6273.md)|Celé číslo Argumen k formátování – funkce|  
|[C6274](../code-quality/c6274.md)|Argument není znak k formátování – funkce|  
|[C6276](../code-quality/c6276.md)|Neplatný řetězec přetypování|  
|[C6277](../code-quality/c6277.md)|Neplatný CreateProcess – volání|  
|[C6284](../code-quality/c6284.md)|Argument neplatný objekt do formátu – funkce|  
|[C6290](../code-quality/c6290.md)|Bitový logický operátor Not- a prioritu|  
|[C6291](../code-quality/c6291.md)|Logický operátor Not bitový- nebo priorit|  
|[C6302](../code-quality/c6302.md)|Argument řetězce neplatný znak k formátování – funkce|  
|[C6303](../code-quality/c6303.md)|Argument řetězce neplatný znak široké k formátování – funkce|  
|[C6305](../code-quality/c6305.md)|Neodpovídající velikost a počet použití|  
|[C6306](../code-quality/c6306.md)|Volání funkce nesprávný argumentů proměnných|  
|[C6328](../code-quality/c6328.md)|Potenciální Neshoda typu argumentů|  
|[C6385](../code-quality/c6385.md)|Přetečení pro čtení|  
|[C6386](../code-quality/c6386.md)|Zápis přetečení|  
|[C6387](../code-quality/c6387.md)|Neplatná hodnota parametru|  
|[C6500](../code-quality/c6500.md)|Vlastnost neplatný atribut|  
|[C6501](../code-quality/c6501.md)|Konfliktní hodnoty vlastností atributu|  
|[C6503](../code-quality/c6503.md)|Odkazy na nemůže mít hodnotu Null|  
|[C6504](../code-quality/c6504.md)|Hodnotu Null u jiných ukazatele|  
|[C6505](../code-quality/c6505.md)|MustCheck na Void|  
|[C6506](../code-quality/c6506.md)|Velikost vyrovnávací paměti na jiný ukazatel nebo pole|  
|[C6508](../code-quality/c6508.md)|Přístup pro zápis na konstanta|  
|[C6509](../code-quality/c6509.md)|Vraťte se používá na předběžnou podmínku.|  
|[C6510](../code-quality/c6510.md)|V jiných ukazatel byl ukončen hodnotu Null|  
|[C6511](../code-quality/c6511.md)|Musí být MustCheck Ano nebo ne|  
|[C6513](../code-quality/c6513.md)|Element velikost bez velikost vyrovnávací paměti|  
|[C6514](../code-quality/c6514.md)|Velikost vyrovnávací paměti překračuje velikost pole|  
|[C6515](../code-quality/c6515.md)|Velikost vyrovnávací paměti na jiný ukazatele|  
|[C6516](../code-quality/c6516.md)|Žádné vlastnosti v atributu|  
|[C6517](../code-quality/c6517.md)|Platné velikost na bez možnosti čtení vyrovnávací paměti|  
|[C6518](../code-quality/c6518.md)|Zapisovatelné velikost na umožňovat zápis vyrovnávací paměti|  
|[C6522](../code-quality/c6522.md)|Neplatná velikost String – typ|  
|[C6525](../code-quality/c6525.md)|Neplatná velikost řetězce nedostupný umístění|  
|[C6527](../code-quality/c6527.md)|Neplatný poznámky: vlastnost 'NeedsRelease' nesmí být použity na hodnoty typu void|  
|[C6530](../code-quality/c6530.md)|Nerozpoznaný formát řetězec styl|  
|[C6540](../code-quality/c6540.md)|Používání atributu poznámky k této funkci zrušíte platnost všech jeho existujících poznámek __declspec|  
|[C6551](../code-quality/c6551.md)|Neplatná velikost Specifikace: výrazu není parsable|  
|[C6552](../code-quality/c6552.md)|Neplatný Deref = nebo Notref =: výrazu není parsable|  
|[C6701](../code-quality/c6701.md)|Hodnota není platná hodnota Ano/Ne nebo možná|  
|[C6702](../code-quality/c6702.md)|Hodnota není hodnotu řetězce|  
|[C6703](../code-quality/c6703.md)|Hodnota není číslem|  
|[C6704](../code-quality/c6704.md)|Chyba výrazu neočekávané poznámky|  
|[C6705](../code-quality/c6705.md)|Očekávaný počet argumentů pro poznámky neodpovídá skutečný počet argumentů pro poznámky|  
|[C6706](../code-quality/c6706.md)|Neočekávaná chyba poznámky pro poznámky|  
|[C28021](../code-quality/c28021.md)|Hodnota parametru se poznámky musí být ukazatel|  
|[C28182](../code-quality/c28182.md)|Vyhodnocení NULOVÝ ukazatel. Ukazatel obsahuje stejnou hodnotu NULL, jako další ukazatel.|  
|[C28202](../code-quality/c28202.md)|Neplatný odkaz na člena nestatické|  
|[C28203](../code-quality/c28203.md)|Nejednoznačný odkaz na člen třídy.|  
|[C28205](../code-quality/c28205.md)|_Success\_ nebo _On_failure\_ použít v kontextu neplatný|  
|[C28206](../code-quality/c28206.md)|Operand body zleva struktury, použijte '->.|  
|[C28207](../code-quality/c28207.md)|Levý operand je struktury, použijte '. "|  
|[C28210](../code-quality/c28210.md)|Poznámky pro daný kontext __on_failure nesmí být v kontextu explicitní před|  
|[C28211](../code-quality/c28211.md)|Byl očekáván pro SAL_context název statickém kontextu|  
|[C28212](../code-quality/c28212.md)|Ukazatele – výraz pro poznámky|  
|[C28213](../code-quality/c28213.md)|_Use_decl_annotations\_ poznámky musí být slouží k odkazování bez úprav, předběžné prohlášení.|  
|[C28214](../code-quality/c28214.md)|Atribut názvy parametrů musí být p1... p9|  
|[C28215](../code-quality/c28215.md)|Typefix nelze použít pro parametr, který již má typefix|  
|[C28216](../code-quality/c28216.md)|CheckReturn poznámky platí jenom pro vstupních parametru konkrétní funkce.|  
|[C28217](../code-quality/c28217.md)|Pro funkci Počet parametrů k poznámky neodpovídá najít v souboru|  
|[C28218](../code-quality/c28218.md)|Pro funkce paramteer poznámky parametr neodpovídá najít v souboru|  
|[C28219](../code-quality/c28219.md)|Očekáván člen výčtu pro poznámky parametr do anotace|  
|[C28220](../code-quality/c28220.md)|Očekáván výraz celé číslo pro poznámky parametr do anotace|  
|[C28221](../code-quality/c28221.md)|Očekávání pro parametr v anotace řetězcového výrazu|  
|[C28222](../code-quality/c28222.md)|__yes \__Ne, nebo \__maybe očekávání pro poznámky|  
|[C28223](../code-quality/c28223.md)|Nebyl nalezen očekávaný Token nebo identifikátor pro poznámky, parametr|  
|[C28224](../code-quality/c28224.md)|Poznámky vyžaduje parametry|  
|[C28225](../code-quality/c28225.md)|Nebyla nalezena správný počet požadovaných parametrů v poznámky|  
|[C28226](../code-quality/c28226.md)|Poznámka nemůže být také PrimOp (v aktuální deklarace)|  
|[C28227](../code-quality/c28227.md)|Poznámka nemůže být také PrimOp (viz předchozí deklarace)|  
|[C28228](../code-quality/c28228.md)|Parametr Poznámka: nelze použít typ v poznámky|  
|[C28229](../code-quality/c28229.md)|Poznámky nepodporuje parametry|  
|[C28230](../code-quality/c28230.md)|Typ parametru nemá žádný člen.|  
|[C28231](../code-quality/c28231.md)|Poznámka je platné jenom pro pole|  
|[C28232](../code-quality/c28232.md)|před, post, nebo deref nevztahuje se na žádné poznámky|  
|[C28233](../code-quality/c28233.md)|před, post, nebo deref u blok|  
|[C28234](../code-quality/c28234.md)|__at výraz nevztahuje na aktuální – funkce|  
|[C28235](../code-quality/c28235.md)|Funkci nelze samostatná jako poznámky|  
|[C28236](../code-quality/c28236.md)|Poznámka nelze použít ve výrazech|  
|[C28237](../code-quality/c28237.md)|Poznámky v parametru se už nepodporuje.|  
|[C28238](../code-quality/c28238.md)|Poznámky v parametru má více než jednu hodnotu, String a Long. Použít paramn = xxx|  
|[C28239](../code-quality/c28239.md)|Poznámky v parametru má hodnotu, String nebo Long; a paramn = xxx. Používat pouze paramn = xxx|  
|[C28240](../code-quality/c28240.md)|Poznámky v parametru má param2, ale žádné param1|  
|[C28241](../code-quality/c28241.md)|Poznámky pro funkce na parametr nebyl rozpoznán.|  
|[C28243](../code-quality/c28243.md)|Poznámka pro funkce v parametru vyžaduje více dereferences než povoluje skutečný typ poznámky.|  
|[C28245](../code-quality/c28245.md)|Poznámky pro funkci označí 'to' na jiný – členské – funkce|  
|[C28246](../code-quality/c28246.md)|Parametr poznámky pro funkci neodpovídá typu parametru|  
|[C28250](../code-quality/c28250.md)|Nekonzistentní poznámky pro funkci: předchozí instance došlo k chybě.|  
|[C28251](../code-quality/c28251.md)|Nekonzistentní poznámky pro funkci: Tato instance došlo k chybě.|  
|[C28252](../code-quality/c28252.md)|Nekonzistentní poznámky pro funkci: parametr má jiné poznámky v této instanci.|  
|[C28253](../code-quality/c28253.md)|Nekonzistentní poznámky pro funkci: parametr má jiné poznámky v této instanci.|  
|[C28254](../code-quality/c28254.md)|(dynamic_cast <>) není podporována v poznámky|  
|[C28262](../code-quality/c28262.md)|Chyba syntaxe v Poznámka byla nalezena ve funkci pro poznámky|  
|[C28263](../code-quality/c28263.md)|Chyby syntaxe v podmíněného poznámky pro vnitřní poznámky nebyl nalezen.| 
|[C28267](../code-quality/c28267.md)|Chyba syntaxe v poznámky nenašel ve funkci poznámky.|  
|[C28272](../code-quality/c28272.md)|Poznámky pro funkce, parametr při zkoumání není konzistentní s deklarace funkce|  
|[C28273](../code-quality/c28273.md)|Pro funkci nejsou konzistentní s deklarace funkce různá vodítka|  
|[C28275](../code-quality/c28275.md)|Parametr pro _Macro_value\_ má hodnotu null.|  
|[C28279](../code-quality/c28279.md)|Pro symbol bez odpovídající 'end' 'začít' nebyl nalezen|  
|[C28280](../code-quality/c28280.md)|Pro symbol byl nalezen 'end' bez odpovídající 'začít.|  
|[C28282](../code-quality/c28282.md)|Řetězce formátu musí být v předběžné podmínky|  
|[C28285](../code-quality/c28285.md)|Pro funkci, Chyba syntaxe v parametru|  
|[C28286](../code-quality/c28286.md)|Pro funkci, Chyba syntaxe v blízkosti end|  
|[C28287](../code-quality/c28287.md)|Pro funkci, Chyba syntaxe v vybr_anou\_poznámky () (Nerozpoznaný parametr název)|  
|[C28288](../code-quality/c28288.md)|Pro funkci, Chyba syntaxe v vybr_anou\_poznámky () (neplatný parametr name)|  
|[C28289](../code-quality/c28289.md)|Pro funkci: ReadableTo nebo WritableTo neměl limit specifikace jako parametr|  
|[C28290](../code-quality/c28290.md)|poznámky pro funkce obsahuje více externích typů než skutečný počet parametrů|  
|[C28291](../code-quality/c28291.md)|po hodnotu null nebo notnull v deref úroveň 0 je smysl pro funkci.|  
|[C28300](../code-quality/c28300.md)|Výraz operandy nekompatibilních typů pro operátor|  
|[C28301](../code-quality/c28301.md)|Žádné poznámky pro první deklaraci funkce.|  
|[C28302](../code-quality/c28302.md)|Navíc _deref –\_ operátor byl nalezen na poznámky.|  
|[C28303](../code-quality/c28303.md)|Nejednoznačný _deref –\_ operátor byl nalezen na poznámky.|  
|[C28304](../code-quality/c28304.md)|Nesprávně umístěné _Notref\_ operátor byl nalezen u tokenu.|  
|[C28305](../code-quality/c28305.md)|Byl zjištěn k chybě při analýze tokenu.|  
|[C28350](../code-quality/c28350.md)|Poznámka popisuje situaci, který není podmíněně dostupná.|  
|[C28351](../code-quality/c28351.md)|Poznámka popisuje, kde dynamické hodnotu (proměnné) nelze použít v podmínce.|