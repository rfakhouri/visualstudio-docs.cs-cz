---
title: "Model aplikace & č. 39; architektura s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: UML, modeling architecture
ms.assetid: aedce746-9df5-49e1-9662-67eb1b83d313
caps.latest.revision: "19"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.workload: multiple
ms.openlocfilehash: 669720bcffe8f33636147863b89c2a28113911c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="model-your-app39s-architecture"></a>Model aplikace & č. 39; architektura s
K zajištění, že software systému nebo aplikace splňuje vašich uživatelů potřebuje, můžete vytvořit modely v sadě Visual Studio jako součást vaší popis celková struktura a chování softwaru systému nebo aplikace. Použití modelů, můžete také popisují vzorů, které se používají v rámci návrhu. Tyto modely vám pomůžou pochopit stávající architektura, popisují změny a vaše záměry jasně komunikovat.  
  
 Tuto funkci podporovat kterou verzí sady Visual Studio najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Účelem modelu je ke snížení nejasnosti, ke kterým došlo v přirozeném jazyce popisy a pomohou vám a vašim kolegům vizualizovat návrh a popisují alternativní návrhy. Model je třeba použít společně s další dokumenty nebo diskusí. Sama o sobě nereprezentuje model specifikaci dokončení architektury.  
  
> [!NOTE]
>  V tomto tématu "systém" znamená software, který vyvíjíte. Může to být velké kolekce mnoho softwarové a hardwarové součásti, nebo jednu aplikaci nebo součástí aplikace.  
  
 Architektura systému je možné rozdělit do dvou oblastech:  
  
-   [Hlavnímu návrhu](#Structure). Popisuje hlavní součásti a jejich vzájemné interakce mezi sebou ke splnění jednotlivých požadavků. Pokud systém je velká, může být jednotlivé komponenty vlastní hlavnímu návrhu, který ukazuje, jak se skládá z menší součásti.  
  
-   [Vzory návrhu](#Patterns) a pravidla týkající se používají v rámci návrhů součásti. Vzor popisuje určitý postup k dosažení programovací cíle. Pomocí stejné vzory v rámci návrh váš tým může snížit náklady na provedení změn a vývoj nový software.  
  
##  <a name="Structure"></a>Hlavnímu návrhu  
 Hlavnímu návrhu popisuje hlavní součásti systému a způsob, jakým interagují s navzájem k dosažení cíle návrhu. Aktivity v následujícím seznamu jsou součástí vývoj nejvyšších úrovní návrhu, i když nemusí v určitém pořadí.  
  
 Při aktualizaci existujícího kódu, může zahájíte popisující hlavní součásti. Zajistěte, aby můžete porozumět veškeré změny požadavků uživatele a pak přidávat nebo upravovat interakce mezi součástmi. Pokud vyvíjíte nový systém, začněte tím, že vysvětlení hlavní funkce potřeby uživatelů. Můžete byste měli prozkoumat pořadí interakce v případech využívá a pak konsolidovat pořadí do součásti návrhu.  
  
 V každém případě je užitečné pro vývoj různé aktivity paralelně a vývoj kódu a testy včas. Vyhněte se pokusům o jednu z těchto aspektů dokončit před zahájením jiné. Obvykle se požadavky a vaše pochopení nástroje nejlepší způsob, jak navrhnout systému se změní při psaní a testování kód. Proto by měl začněte tím, že vysvětlení a kódování hlavní funkce požadavků a návrhu. Zadejte podrobnosti v novější iterací projektu.  
  
-   [Seznámení s požadavky na](#Requirements). Výchozí bod žádné návrhu je jasné potřeby uživatelů.  
  
-   [Architektury vzory](#BigDecisions). Volby provedené o základní technologie a prvky architektury systému.  
  
-   Datový Model součásti a rozhraní. Diagramy tříd k popisu informace, které je předán mezi součástmi a uložený v součásti můžete kreslení.  
  
##  <a name="Requirements"></a>Seznámení s požadavky na  
 Hlavnímu návrhu dokončení aplikace efektivní vyvinutý společně s požadavky na modelu nebo jiných popis potřeby uživatelů. Další informace o modelech požadavky najdete v tématu [modelování uživatelských požadavků](../modeling/model-user-requirements.md).  
  
 Pokud je systém, které vyvíjíte součást větší systému, může být část nebo všechny vaše požadavky shrnuta v programovací rozhraní.  
  
 Požadavky na modelu poskytuje tyto základní údaje:  
  
-   K dispozici rozhraní. Zadané rozhraní zobrazí seznam služeb nebo operace, které systém nebou součást musí poskytovat uživatelům, ať už jsou lidské uživatele nebo další softwarové součásti.  
  
-   Požadovaným rozhraním. Požadované rozhraní zobrazí seznam služeb nebo operace, které můžete použít systém nebou součást. V některých případech bude možné navrhnout těchto služeb v rámci vlastní systému. V ostatních případech zvlášť pokud navrhujete komponenty, která lze spojovat s dalšími součástmi v řadě konfigurací požadované rozhraní bude nastavit externí aspekty.  
  
-   Kvality služeb požadavky. Výkon, zabezpečení, odolnosti a jiné cíle a omezení, které musí splňovat systému.  
  
 Požadavky na modelu se zapíše z hlediska uživatelů vašeho systému, ať už osoby nebo další softwarové součásti. Věděli, nic vnitřní strukturu a funkci systému. Vaším cílem v architektuře modelu naopak je, a popisuje strukturu a interní funkci ukazují, jak splňují uživatelů potřebuje.  
  
 Pokud oddělíte požadavků a architektury modely je užitečná, protože umožňuje jednodušší popisují požadavky s uživateli. Také pomáhá Refaktorovat návrh a zvažte alternativní architektury při zachování požadavky beze změny.  
  
 Množství podrobností, které byste měli umístit do požadavky nebo Architektonický model závisí na rozsahu projektu a velikosti a distribuci týmu. Žádné další než zobrazení diagramu tříd obchodní koncepty a některé vzory návrhu; přejít malých týmů na krátké projektu Nový projekt distribuovány na více než jedné oblasti potřebovat výrazně podrobněji.  
  
##  <a name="BigDecisions"></a>Vzory architektury  
 Časná ve vývojovém budete muset zvolit hlavní technologie a elementy, na kterých závisí návrhu. Oblasti, ve kterých je nutné provést tyto možnosti zahrnují následující:  
  
-   Základní možnosti, které technologie, jako je výběr mezi databází a systém souborů a volba mezi aplikace v síti a webovému klientovi a tak dále.  
  
-   Možnosti rozhraní, jako je například volba mezi Windows Workflow Foundation nebo ADO.NET Entity Framework.  
  
-   Metoda volby integrace, například mezi sběrnici služby enterprise nebo kanál typu point-to-point.  
  
 Tyto možnosti často určuje kvalitu služeb požadavky například škálování a flexibilitu a můžete provést před podrobné požadavky jsou známé. Ve velkých systému jsou vzájemně důrazně souvisejících konfigurace hardwaru a softwaru.  
  
 Možnosti, které provedete vliv na způsob používání a interpretace Architektonický model. Například v rámci systému, která používá databázi přidružení v diagramu tříd může představovat vztahů nebo cizí klíče v databázi, zatímco v systému, který je založen na soubory XML, může znamenat přidružení křížové odkazy, které používají XPath. V distribuované systému může představovat zpráv v diagramu pořadí zprávy v přenosu; samostatná aplikace může představovat volání funkcí.  
  
##  <a name="Patterns"></a>Vzory návrhu  
 Vzor návrhu je přehled o tom, jak navrhnout určitý aspekt softwaru, hlavně ten, který objeví znovu v různých částech systému. Přijetím jednotný přístup v projektu může snížit náklady na návrh, zajištění konzistence v uživatelském rozhraní a snížit náklady na pochopení a změna kódu.  
  
 Jsou některé obecné návrhu vypadají podobně jako pozorovatel dobře známé a široce použitelné. Kromě toho jsou vzorů, které se vztahují pouze k projektu. Například ve webové prodeje systému, budou existovat několik operací v kódu kde změn pořadí zákazníka. Aby se zajistilo, že se stav pořadí přesně zobrazí v každé fázi, musí všechny tyto operace podle konkrétní protokol k aktualizaci databáze.  
  
 Součást pracovní architektury softwaru je určit, co by měl být vzory přijaly napříč návrhu. Je to obvykle probíhající úlohy, protože nové vzory a vylepšení existující vzory budou zjištěny průběhu projektu. Je užitečné k uspořádání vývoj plán tak, aby každý vašim vzorům hlavní návrhu prověření včas.  
  
 Většina vzory návrhu může být částečně shrnuta v kódu framework. Část vzorce se může snížit vyžadováním vývojáři použít konkrétní třídy nebo součásti, například vrstva přístupu k databázi, která zajišťuje, že je databáze správně zpracovat.  
  
 Vzor návrhu je popsané v dokumentu a obvykle zahrnuje tyto části:  
  
-   Jméno.  
  
-   Popis kontext, ve které se vztahuje. Jaké kritéria by měl vytvořit vývojář, zvažte použití tohoto vzoru?  
  
-   Stručné vysvětlení problému, který řeší.  
  
-   Modelu hlavní části a jejich vztahů. To může být třídy nebo součásti a rozhraní, se přidružení a závislosti mezi nimi. Elementy obvykle spadají do dvou kategorií:  
  
-   Zásady vytváření názvů.  
  
-   Popis jak vzoru řeší problém.  
  
-   Popis varianty, které se můžou vývojáři moci přijmout.  
  
## <a name="see-also"></a>Viz také  
 [Vizualizace kódu](../modeling/visualize-code.md)   
 [Modelování uživatelských požadavků](../modeling/model-user-requirements.md)   
 [Vývoj testů z modelu](../modeling/develop-tests-from-a-model.md)   
 [Použití modelů ve vývojových procesech](../modeling/use-models-in-your-development-process.md)