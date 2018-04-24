---
title: Sada pravidel Nativní doporučená pravidla
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a2fff799001f9fdffb9dde52785e08239d363d9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="native-recommended-rules-rule-set"></a>Sada pravidel Nativní doporučená pravidla

Nativní doporučená pravidla se zaměřit na nejvíce kritické a běžné problémy v nativním kódu, včetně potenciální bezpečnostní díry a dojde k chybě aplikace. Toto pravidlo nastavit v žádné sadě vlastní pravidlo, že které vytvoříte pro nativní projekty by měla obsahovat.

|Pravidlo|Popis|
|----------|-----------------|
|[C6001](../code-quality/c6001.md)|Pomocí neinicializované paměti|
|[C6011](../code-quality/c6011.md)|Vyhodnocení ukazatele Null.|
|[C6029](../code-quality/c6029.md)|Nezaškrtnuté hodnota|
|[C6031](../code-quality/c6031.md)|Návratová hodnota ignorována|
|[C6053](../code-quality/c6053.md)|Nulové ukončení z volání|
|[C6054](../code-quality/c6054.md)|Nula chybí ukončení|
|[C6059](../code-quality/c6059.md)|Chybný zřetězení|
|[C6063](../code-quality/c6063.md)|Chybí Argument řetězce k formátování – funkce|
|[C6064](../code-quality/c6064.md)|Chybí Argument celé číslo k formátování – funkce|
|[C6066](../code-quality/c6066.md)|Chybí Argument ukazatele k formátování – funkce|
|[C6067](../code-quality/c6067.md)|Chybí Argument řetězce ukazatele k formátování – funkce|
|[C6101](../code-quality/c6101.md)|Vrácení neinicializované paměti|
|[C6200](../code-quality/c6200.md)|Index překračuje maximální vyrovnávací paměti|
|[C6201](../code-quality/c6201.md)|Index překračuje maximální zásobníku vyrovnávací paměti|
|[C6214](../code-quality/c6214.md)|Neplatné obsazení HRESULT na BOOL|
|[C6215](../code-quality/c6215.md)|Neplatné obsazení BOOL k HRESULT|
|[C6216](../code-quality/c6216.md)|Neplatné obsazení vložit kompilátoru BOOL k HRESULT|
|[C6217](../code-quality/c6217.md)|Neplatný HRESULT testu s není|
|[C6220](../code-quality/c6220.md)|Neplatný HRESULT porovnat hodnotu -1|
|[C6226](../code-quality/c6226.md)|Neplatný HRESULT přiřazení na hodnotu -1|
|[C6230](../code-quality/c6230.md)|Neplatný HRESULT použijte jako logická hodnota|
|[C6235](../code-quality/c6235.md)|Konstanta nenulové s logické- nebo|
|[C6236](../code-quality/c6236.md)|Logický – nebo s nenulovou hodnotou konstanta|
|[C6237](../code-quality/c6237.md)|Nula s logické- a ztratí vedlejší efekty|
|[C6242](../code-quality/c6242.md)|Místní Unwind vynutit|
|[C6248](../code-quality/c6248.md)|Vytváření DACL hodnotu Null.|
|[C6250](../code-quality/c6250.md)|Popisovače nevydané adresa|
|[C6255](../code-quality/c6255.md)|Nechráněné použití alloca –|
|[C6258](../code-quality/c6258.md)|Pomocí ukončení vláken|
|[C6259](../code-quality/c6259.md)|Mrtvých kód na bitový- nebo jsou omezena přepínače|
|[C6260](../code-quality/c6260.md)|Použití aritmetické bajtů|
|[C6262](../code-quality/c6262.md)|Použití nadměrné zásobníku|
|[C6263](../code-quality/c6263.md)|Pomocí alloca – ve smyčce|
|[C6268](../code-quality/c6268.md)|Chybí závorky v přetypování|
|[C6269](../code-quality/c6269.md)|Zrušení ukazatele ignorovat|
|[C6270](../code-quality/c6270.md)|Chybí Argument Float k formátování – funkce|
|[C6271](../code-quality/c6271.md)|Nadbytečný Argument k formátování – funkce|
|[C6272](../code-quality/c6272.md)|Argument typu Float k formátování – funkce|
|[C6273](../code-quality/c6273.md)|Argument celé číslo k formátování – funkce|
|[C6274](../code-quality/c6274.md)|Argument není znak k formátování – funkce|
|[C6276](../code-quality/c6276.md)|Neplatný řetězec přetypování|
|[C6277](../code-quality/c6277.md)|Neplatný CreateProcess – volání|
|[C6278](../code-quality/c6278.md)|Neshoda nové pole skalární odstranění|
|[C6279](../code-quality/c6279.md)|Neshoda skalárních nové pole odstranění|
|[C6280](../code-quality/c6280.md)|Neshoda navrácení přidělení paměti|
|[C6281](../code-quality/c6281.md)|Priorita bitové vztah|
|[C6282](../code-quality/c6282.md)|Přiřazení nahrazuje testu|
|[C6283](../code-quality/c6283.md)|Primitivní neshoda nové pole skalární odstranění|
|[C6284](../code-quality/c6284.md)|Argument neplatný objekt do formátu – funkce|
|[C6285](../code-quality/c6285.md)|Logické- nebo konstant|
|[C6286](../code-quality/c6286.md)|Nulová logické- nebo došlo ke ztrátě vedlejší efekty|
|[C6287](../code-quality/c6287.md)|Redundantní testu|
|[C6288](../code-quality/c6288.md)|Vzájemné zahrnutí přes logické- a je hodnota False|
|[C6289](../code-quality/c6289.md)|Vzájemné vyloučení přes logické- nebo hodnotu True|
|[C6290](../code-quality/c6290.md)|Bitový logický operátor Not- a prioritu|
|[C6291](../code-quality/c6291.md)|Logický operátor Not bitový- nebo priorit|
|[C6292](../code-quality/c6292.md)|Až od maximální počty smyčky|
|[C6293](../code-quality/c6293.md)|Smyčky počty z minimální|
|[C6294](../code-quality/c6294.md)|Nikdy provést těla smyčky|
|[C6295](../code-quality/c6295.md)|Nekonečná smyčka|
|[C6296](../code-quality/c6296.md)|Spustit pouze jednou smyčky|
|[C6297](../code-quality/c6297.md)|Výsledek Shift přetypovat na větší velikost|
|[C6299](../code-quality/c6299.md)|Bitfield k porovnání Boolean|
|[C6302](../code-quality/c6302.md)|Argument řetězce neplatný znak k formátování – funkce|
|[C6303](../code-quality/c6303.md)|Argument řetězce neplatný znak široké k formátování – funkce|
|[C6305](../code-quality/c6305.md)|Neodpovídající velikost a počet použití|
|[C6306](../code-quality/c6306.md)|Volání funkce nesprávný argumentů proměnných|
|[C6308](../code-quality/c6308.md)|Realloc – úniku|
|[C6310](../code-quality/c6310.md)|Neplatný výjimka filtru konstanta|
|[C6312](../code-quality/c6312.md)|Výjimka pokračovat v provádění smyčky|
|[C6314](../code-quality/c6314.md)|Bitový- nebo priorit|
|[C6317](../code-quality/c6317.md)|Není není doplňku|
|[C6318](../code-quality/c6318.md)|Výjimka pokračovat v hledání|
|[C6319](../code-quality/c6319.md)|Ignorovat čárkou|
|[C6324](../code-quality/c6324.md)|Řetězec kopírování místo porovnat řetězec|
|[C6328](../code-quality/c6328.md)|Potenciální Neshoda typu argumentů|
|[C6331](../code-quality/c6331.md)|Virtualfree – neplatné příznaky|
|[C6332](../code-quality/c6332.md)|Virtualfree – neplatný parametr|
|[C6333](../code-quality/c6333.md)|Virtualfree – neplatná velikost|
|[C6335](../code-quality/c6335.md)|Úniku popisovač procesu|
|[C6381](../code-quality/c6381.md)|Chybí informace o vypnutí|
|[C6383](../code-quality/c6383.md)|Element – počet bajtů-Počet přetečení vyrovnávací paměti|
|[C6384](../code-quality/c6384.md)|Dělení velikost ukazatele|
|[C6385](../code-quality/c6385.md)|Přetečení pro čtení|
|[C6386](../code-quality/c6386.md)|Zápis přetečení|
|[C6387](../code-quality/c6387.md)|Neplatná hodnota parametru|
|[C6388](../code-quality/c6388.md)|Neplatná hodnota parametru|
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
|[C6995](../code-quality/c6995.md)|Nepovedlo se uložit soubor protokolu XML|
|[C26100](../code-quality/c26100.md)|Časování|
|[C26101](../code-quality/c26101.md)|Selhání správně používat interlocked operace|
|[C26110](../code-quality/c26110.md)|Volající selhání k uchování uzamčení|
|[C26111](../code-quality/c26111.md)|Nedaří se uvolnit zámek volajícího|
|[C26112](../code-quality/c26112.md)|Volající nemůže obsahovat žádné zámku|
|[C26115](../code-quality/c26115.md)|Chcete-li uvolnit zámek selhání|
|[C26116](../code-quality/c26116.md)|Selhání získat nebo k uchování uzamčení|
|[C26117](../code-quality/c26117.md)|Uvolnění unheld zámku|
|[C26140](../code-quality/c26140.md)|Chyba poznámky SAL souběžnosti|
|[C28020](../code-quality/c28020.md)|Výraz není true na toto volání|
|[C28021](../code-quality/c28021.md)|Hodnota parametru se poznámky musí být ukazatel|
|[C28022](../code-quality/c28022.md)|Třídami funkce, které jsou k této funkci se neshodují s třídami, které jsou funkce na typedef používá k definování ho.|
|[C28023](../code-quality/c28023.md)|Funkce se přiřazené nebo předán by měl mít _Function_class\_ poznámky pro minimálně jeden třídami, které jsou|
|[C28024](../code-quality/c28024.md)|Ukazatel funkce, které jsou přiřazeny je označena třídu funkce, která není obsažen v seznamu třídy funkce.|
|[C28039](../code-quality/c28039.md)|Typ skutečný parametr přesně shodovat s typem|
|[C28112](../code-quality/c28112.md)|Proměnné, které je přístupné prostřednictvím funkce Interlocked musí vždy přístup prostřednictvím funkce Interlocked.|
|[C28113](../code-quality/c28113.md)|Přístup k místní proměnné prostřednictvím funkce Interlocked|
|[C28125](../code-quality/c28125.md)|Funkce musí být volána z v rámci bloku try / kromě bloku|
|[C28137](../code-quality/c28137.md)|Proměnné argument musí být místo toho (literálu) Konstanta|
|[C28138](../code-quality/c28138.md)|Konstantní argument měla by být proměnné|
|[C28159](../code-quality/c28159.md)|Zvažte použití jinou funkci.|
|[C28160](../code-quality/c28160.md)|Chyba – Poznámka|
|[C28163](../code-quality/c28163.md)|Funkce by měla být volána z nikdy, v rámci bloku try / kromě bloku|
|[C28164](../code-quality/c28164.md)|Probíhá argument předaný funkci, která očekává ukazatel na objekt (nikoli ukazatel na ukazatel)|
|[C28182](../code-quality/c28182.md)|Vyhodnocení NULOVÝ ukazatel. Ukazatel obsahuje stejnou hodnotu NULL, jako další ukazatel.|
|[C28183](../code-quality/c28183.md)|Argument může být jedna hodnota a je kopii hodnota nalezena v ukazatele|
|[C28193](../code-quality/c28193.md)|Proměnná obsahuje hodnotu, která musí být zkontrolován|
|[C28196](../code-quality/c28196.md)|Požadavek není splněná. (Výraz nelze vyhodnotit na hodnotu true.)|
|[C28202](../code-quality/c28202.md)|Neplatný odkaz na člena nestatické|
|[C28203](../code-quality/c28203.md)|Nejednoznačný odkaz na člen třídy.|
|[C28205](../code-quality/c28205.md)|_Success\_ nebo _On_failure\_ použít v kontextu neplatný|
|[C28206](../code-quality/c28206.md)|Operand body zleva struktury, použijte '->.|
|[C28207](../code-quality/c28207.md)|Levý operand je struktury, použijte '. "|
|[C28209](../code-quality/c28209.md)|Deklarace pro symbol má konfliktní deklarace|
|[C28210](../code-quality/c28210.md)|Poznámky pro daný kontext __on_failure nesmí být v kontextu explicitní před|
|[C28211](../code-quality/c28211.md)|Byl očekáván pro SAL_context název statickém kontextu|
|[C28212](../code-quality/c28212.md)|Ukazatele – výraz pro poznámky|
|[C28213](../code-quality/c28213.md)|_Use_decl_annotations\_ poznámky musí být slouží k odkazování bez úprav, předběžné prohlášení.|
|[C28214](../code-quality/c28214.md)|Atribut názvy parametrů musí být p1... p9|
|[C28215](../code-quality/c28215.md)|Typefix nelze použít pro parametr, který již má typefix|
|[C28216](../code-quality/c28216.md)|CheckReturn poznámky platí jenom pro vstupních parametru konkrétní funkce.|
|[C28217](../code-quality/c28217.md)|Pro funkci Počet parametrů k poznámky neodpovídá najít v souboru|
|[C28218](../code-quality/c28218.md)|Pro parametr funkce poznámky parametr neodpovídá najít v souboru|
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
|[C28244](../code-quality/c28244.md)|Poznámky pro funkci má nelze analyzovat parametr/externí poznámky|
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
|[C28306](../code-quality/c28306.md)|Poznámky v parametru je obsolescent|
|[C28307](../code-quality/c28307.md)|Poznámky v parametru je obsolescent|
|[C28350](../code-quality/c28350.md)|Poznámka popisuje situaci, který není podmíněně dostupná.|
|[C28351](../code-quality/c28351.md)|Poznámka popisuje, kde dynamické hodnotu (proměnné) nelze použít v podmínce.|