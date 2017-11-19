---
title: "Visual C++ pro vývoj pro různé platformy mobilních | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0bb872d6-981b-4c96-9143-fcec5336bf0d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 51b579d047987648caab31136b6378e0a6f0475d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visual-c-for-cross-platform-mobile-development"></a>Visual C++ pro vývoj mobilních pro různé platformy
Můžete vytvářet nativní aplikace C++ pro iOS, Android a Windows zařízení a společný kód sdílené složky v knihovnách vytvořené pro iOS, Android a Windows pomocí Visual C++ pro vývoj mobilních řešení pro různé platformy. Toto je možnost k dispozici ve Visual Studiu 2015, který nainstaluje sady SDK a nástroje, které jsou potřeba pro vývoj pro různé platformy sdílené knihovny a nativní aplikace. Při instalaci, můžete vytvořit kód, který běží na iOS a zařízení se systémem Android a platformy kromě Windows, Windows Phone a Xbox Visual C++.  
  
 Psaní kódu pro různé platformy může být frustrující. Primární programovacích jazyků a nástroje pro iOS, Android a Windows se liší na každou platformu. Ale všechny platformy podporují psaní kódu v jazyce C++. To je běžné jmenovatel, která můžete povolit opakované použití kódu základní napříč platformami. Nativní kód napsaný v jazyce C++ může být i další původce a odolná reverse inženýrství. Opětovné použití kódu můžete uložit čas a úsilí, při vytváření aplikací pro různé platformy.  
  
 Vývoj pomocí Visual C++ pro vývoj mobilních řešení pro různé platformy má několik výhod:  
  
1.  **Snadná instalace.** Instalační program sady Visual Studio operace čtení a nainstaluje požadované nástroje třetích stran a sady SDK, které potřebujete k vytvoření knihovny nebo aplikace pro Android a iOS. Konfigurace a instalace je jednoduchý a většinou automatické.  
  
2.  **Prostředí sestavení výkonný a seznámit.** Lze sdílet napříč platformami řešení a projekty můžete jednoduše vytvořte pomocí šablony sady Visual Studio. Spravujte vlastnosti pro všechny projekty pomocí jednoho společné rozhraní. Upravit všechny kódu v editoru Visual Studio a využít integrované IntelliSense a platformy pro doplňování kódu a chyba zvýraznění.  
  
3.  **Jednotné prostředí pro ladění.** Sledování a krok prostřednictvím kódu C++ na všech platformách, včetně zařízení se systémem Android a emulátorů, simulátoru iOS a zařízení a zařízení s Windows nebo Windows Phone a emulátorů pomocí špičkových ladění nástrojů v sadě Visual Studio.  
  
## <a name="get-the-tools"></a>Získat nástroje  
 Visual C++ pro vývoj mobilních řešení pro různé platformy je instalovat možnost, která se dodává s Visual Studio 2015. Požadavky a pokyny k instalaci najdete v tématu [nainstalovat Visual C++ pro vývoj mobilních řešení pro různé platformy](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). K vytvoření kódu pro iOS, potřebujete také do počítače Mac a Apple iOS vývojářský účet. Další informace najdete v tématu [instalaci a konfiguraci nástroje pro sestavení pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md).  
  
## <a name="come-up-to-speed"></a>Pocházet urychlit  
 Pokud jste pocházejících z vývoj pro Android nebo iOS, máme některé skvělé materiály o tom, jak začít pracovat. Visual Studio se prostředí výrazovou a umožňující vývoj. Chcete-li zjistit, jak používat, zkuste [Začínáme pro vývojáře v systému Android](https://msdn.microsoft.com/en-us/library/windows/apps/dn275875.aspx) nebo [Začínáme pro vývojáře iOS](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/jj657966.aspx). Tato témata vás seznámí s Visual Studio a koncepty, že budete potřebovat k vývoji aplikací pro různé platformy pro Windows a Windows Phone. Pokud chcete začít, zápis první multiplatformní aplikace pro iOS a Android, najdete v části [sestavení aplikace OpenGL ES pro Android a iOS](../cross-platform/build-an-opengl-es-application-on-android-and-ios.md).  
  
 Visual C++ pro vývoj mobilních řešení pro různé platformy obsahuje několik šablon můžete začít pracovat na vašich aplikací:  
  
-   OpenGLES 2 aplikace (Android, iOS, univerzální pro Windows)  
  
     Vytvoří řešení, které obsahuje sadu projekty k vytvoření aplikace pro Android nativní aktivity, aplikaci pro iOS a aplikace pro Universal Windows, společně s sdílené knihovny kódu C++. Tyto aplikace použít knihovny specifických pro platformy, které jsou vytvořené pomocí společný kód C++ OpenGL ES kreslení na stejnou datovou krychli roztočený v každé aplikaci. Nástroje pro vývoj aplikací systému Windows Universal možnost musí obsahovat, když instalujete Visual Studio pro použití této šablony.  
  
-   Aktivita nativní aplikace (Android)  
  
     Vytvoří kompletní aplikace C++ OpenGL jako projekt Android nativní aktivity.  
  
-   OpenGLES aplikace (Android, iOS)  
  
     Vytvoří řešení se sadou projekty k vytvoření aplikace pro iOS i Android nativní aktivity aplikace. Tyto aplikace použít knihovny specifických pro platformy, které jsou vytvořené pomocí společný kód C++ OpenGL ES kreslení na stejnou datovou krychli roztočený v každé aplikaci.  
  
-   Sdílené knihovny (Android, iOS)  
  
     Vytvoří řešení s projekty k vytvoření soubor Android dynamické knihovny (.so) a soubor statické knihovny (.a) s iOS pomocí společného kódu C++ v sdílený projekt.  
  
-   Základní aplikační (Android, Ant)  
  
     Vytvoří Android "Hello, World" projekt aplikace, který používá jen Java zdrojový kód a Ant sestavení systému.  
  
-   Základní aplikační (Android, Gradle)  
  
     Vytvoří Android "Hello, World" projekt aplikace, který používá jen Java zdrojového kódu a Gradle vytváření systému.  
  
-   Základní knihovna (Android, Ant)  
  
     Vytvoří Android "Hello, World" projektu knihovny, který používá jen Java zdrojový kód a Ant sestavení systému.  
  
-   Základní knihovna (Android, Gradle)  
  
     Vytvoří Android "Hello, World" projektu knihovny, který používá jen Java zdrojového kódu a Gradle vytváření systému.  
  
-   Dynamické sdílené knihovny (Android)  
  
     Vytvoří soubor Android dynamické knihovny (.so) pomocí kódu C++.  
  
-   OpenGLES 2 aplikace (iOS)  
  
     Vytvoří řešení se sadou projekty k vytvoření aplikace pro iOS OpenGL ES 2. Aplikace používá knihovnu kódu C++ OpenGL ES k vykreslení roztočený datové krychle v aplikaci pro iOS. Tato aplikace může být to dobrý výchozí bod pro zobrazuje, jak importovat knihovny jazyka C++ do vaší aplikace pro iOS.  
  
-   Statické knihovny (Android)  
  
     Vytvoří projekt sestavit statické knihovny pro Android. Můžete pouze jeden dynamické knihovny v aplikaci pro Android, ale můžete propojit libovolný počet statických knihoven.  
  
-   Statické knihovny (iOS)  
  
     Vytvoří projekt sestavit statické knihovny pro iOS.  
  
-   Projektem souboru pravidel (Android)  
  
     Vytvoří obálku projektu pro Android makefile projekty.  
  
## <a name="try-out-sample-code"></a>Vyzkoušet ukázkový kód  
 Stáhněte si ukázky, které ukazují, jak vytvořit knihovny sdíleného kódu, které můžete použít v systému Windows, Android a iOS aplikace a jak vytvořit dokončení aktivity nativní aplikace pro Android. Abyste mohli začít, najdete v části [příklady vývoj pro různé platformy mobilních](../cross-platform/cross-platform-mobile-development-examples.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
1.  [Instalace Visual C++ pro vývoj mobilních pro různé platformy](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)  
  
2.  [Instalace a konfigurace nástroje pro sestavení pomocí iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md)  
  
3.  [Vytvoření aplikace pro Android nativní aktivity](../cross-platform/create-an-android-native-activity-app.md)  
  
4.  [Sestavení aplikace OpenGL ES pro Android a iOS](../cross-platform/build-an-opengl-es-application-on-android-and-ios.md)  
  
5.  [Příklady mobilní vývoj pro různé platformy](../cross-platform/cross-platform-mobile-development-examples.md)