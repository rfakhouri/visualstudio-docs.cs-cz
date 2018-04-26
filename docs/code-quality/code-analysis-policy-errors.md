---
title: Chyby zásad Analýzy kódu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- vs.codeanalysis.policyfailures
helpviewer_keywords:
- policy errors, code analysis
ms.assetid: d1f221cd-68c0-4277-9397-b76ad0dbae77
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ac981d51dd11b03d7ce35f2583f2c91274129714
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="code-analysis-policy-errors"></a>Chyby zásad Analýzy kódu
Následující chyby dojít, pokud zásady pro analýzu kódu nesplněno při vrácení se změnami:

 **Nastavení analýzy kódu pro jeden nebo více projektů nejsou kompatibilní se zásadami analýza kódu.**

 Pro jeden nebo více projektů kód nebyl splněny požadavky na kód analysis změnami do týmového projektu zdrojového kódu. Tato chyba může být způsobeno jeden nebo více z následujících podmínek:

1.  Analýza kódu není povolená na sestavení pro všechny projekty v řešení.

2.  Místní pravidlo nastavené pro projekt v sadě Visual Studio je méně omezující **akce** nastavení než sady pravidel projektu team, například pravidlo, které je nastaven na **akce**=**chyba**  na serveru má jeho **akce** nastavena na **upozornění** nebo **žádné** v pravidle nastavit spuštěn v sadě Visual Studio).

3.  Sada zadaný v sadě Visual Studio pravidel neobsahuje všechna pravidla, které jsou uvedené v tomto pravidle nastavit zadaný v analýza kódu vrácení se změnami zásad pro týmový projekt.

 **Analýza kódu zásad se nezdařilo. V projektu jsou chyby {0} nebo sestavení není aktuální.**

 Buď sestavení obsahuje chyby, nebo jsme vyřešili chyby, ale nebyla provedena analýza kódu po opravu.

 **Vrácení se změnami se nezdařilo. Zásady pro analýzu kódu vyžaduje, aby se změnami pomocí sady Visual Studio otevřete řešení.**

 Zásady pro analýzu kódu vyžaduje, aby všechny soubory se změnami musí být v aktuálně otevřených řešení. Chcete-li opravit tuto chybu, otevřete řešení, která obsahuje soubor se změnami.

 **Ne všechny soubory v čeká na vrácení se změnami jsou v aktuálně otevřených řešení.**

 Zásady pro analýzu kódu vyžaduje, aby všechny soubory se změnami musí být v aktuálně otevřených řešení. Tato chyba se vyvolá, když je otevřete řešení, ale některé soubory v zobrazení "čeká na vrácení se změnami" nejsou součástí aktuálně otevřenou řešení. Chcete-li opravit tuto chybu, otevřete řešení, která obsahuje soubor se změnami.

 **Verze '{0}' není správný. Je silného názvu určená v zásadách '{1}'.**

 Tato chyba se vztahují na projekty rozhraní .NET. Pravidlo .dll, vyžadují zásady pro analýzu kódu existuje v místním počítači, ale verze nebo veřejný klíč neodpovídá. Chcete-li tuto chybu, musíte aktualizovat tvůrce zásad jeho spuštěním v *C:\Program Files\Microsoft Visual Studio 8\Team Tools\Static Analysis Tools\FxCop\Rules\\*  adresář na svém počítači.

 **'{0}' sestavení určená v zásadách neexistuje.**

 Tato chyba se vztahují na projekty rozhraní .NET. Pravidlo vyžadují zásady pro analýzu kódu nemá odpovídající knihovny dll, které jsou nainstalované v klientském počítači. Opravte tuto chybu, musíte aktualizovat zásady tvůrce knihovny dll v *C:\Program Files\Microsoft Visual Studio 8\Team Tools\Static Analysis Tools\FxCop\Rules\\*  adresář na svém počítači.

 **Projekt {0} pravidla nastavení nejsou v souladu se zásadami analýza kódu.**

 Tato chyba se vztahují na projekty rozhraní .NET. Nastavení pravidel spravovaného kódu nejsou jako přísné jako zásady vyžaduje. Chcete-li tuto chybu, nastavení klienta musí být stejné nebo přísnější než požadavek zásady na serveru.

 **Analýza kódu není povolená na aktivní konfigurace. Přepněte do konfigurace {0} a sestavení projektu {1} před vrácením se změnami.**

 V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], aktivní konfigurace nemá povoleno analýza kódu, ale existuje alespoň jeden kód analýza povolena.

 **Je nutné povolit analýzy kódu pro spravovaný binární soubory v projektu {0} vlastnosti a sestavení před vrácením se změnami.**

 Tato chyba se týká [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] aplikací .NET. Zásady vyžaduje provést analýzu spravovaného kódu, ale není povolený v aktuálním projektu na straně klienta.

 **Je nutné povolit analýza kódu v projektu {0} vlastnosti a sestavení před vrácením se změnami.**

 Tato chyba u [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projekty a webové projekty. Zásady vyžaduje provést analýzu spravovaného kódu, ale není povolený v aktuálním projektu na straně klienta.

 **Analýza kódu C/C++, musíte povolit v projektu {0} vlastnosti a sestavení před vrácením se změnami.**

 Tato chyba se vztahují na projekty nespravované. Zásady pro analýzu kódu vyžaduje analýzy kódu pro C/C++, ale není povolený v aktuálním projektu na straně klienta.

## <a name="see-also"></a>Viz také
 [Chyby aplikace Analýzy kódu](../code-quality/code-analysis-application-errors.md)