---
title: Nástroje pro lokalizaci
ms.date: 02/15/2019
ms.topic: reference
helpviewer_keywords:
- globalization [Visual Studio]
- Visual Basic code, international applications
- C#, international applications
- localization [Visual Studio]
- world-ready applications
- international applications [Visual Studio]
ms.assetid: 4d9815ae-3e80-4b4d-933d-f8309aee18d5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 934427c2bfba769968b7aeb364625b71af47eca7
ms.sourcegitcommit: 51dad3e11d7580567673e0d426ab3b0a17584319
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/10/2019
ms.locfileid: "66820866"
---
# <a name="develop-globalized-and-localized-apps"></a>Vývoj globalizovaných a lokalizovaných aplikací

Visual Studio usnadňuje vývoj pro mezinárodní snadno cílovou skupinu s využitím služeb, které jsou součástí [.NET](/dotnet/standard/globalization-localization/).

Například projektový systém pro aplikace Windows Forms může generovat soubory prostředků pro použití náhradní lokality jazykové verze uživatelského rozhraní a každé další jazykové verze uživatelského rozhraní. Při sestavování projektu v sadě Visual Studio se soubory prostředků jsou kompilovány z formátu XML pro Visual Studio (.resx) do zprostředkující binární formát (.resources), které pak jsou vloženy do satelitních sestavení. Další informace najdete v tématu [soubory prostředků v sadě Visual Studio](/dotnet/framework/resources/creating-resource-files-for-desktop-apps#VSResFiles) a [vytvořit satelitní sestavení pro aplikace klasické pracovní plochy](/dotnet/framework/resources/creating-satellite-assemblies-for-desktop-apps).

## <a name="bidirectional-languages"></a>Obousměrné jazyky

Visual Studio můžete vytvářet aplikace pro správné zobrazení textu v jazycích napsané-doleva, včetně arabština a hebrejština. Pro některé funkce stačí nastavit vlastnosti. V ostatních případech je nutné implementovat v kódu funkce.

> [!NOTE]
> Pokud chcete zadat a zobrazit obousměrných jazyků, musíte pracovat s verzí Windows, který je nakonfigurován příslušný jazyk. To může být buď anglickou verzi systému Windows s odpovídající jazyková sada nainstalovaná nebo správně lokalizovanou verzi Windows.

### <a name="apps-that-support-bidirectional-languages"></a>Aplikace, které podporují obousměrné jazyky

- Aplikace Windows

   Můžete vytvořit plně obousměrné aplikace, které zahrnují podporu pro obousměrný text zprava doleva pořadí čtení a zrcadlení (reverzní rozložení windows, nabídek, dialogová okna a tak dále). S výjimkou zrcadlení, tyto funkce jsou dostupné ve výchozím nastavení nebo nastavení vlastností. Zrcadlení se podporuje ze své podstaty pro některé funkce, jako jsou okna se zprávou. Ale v ostatních případech je nutné implementovat zrcadlení v kódu. Další informace najdete v tématu [obousměrná podpora pro aplikace Windows Forms](/dotnet/framework/winforms/advanced/bi-directional-support-for-windows-forms-applications).

- Webové aplikace

   Webové služby podporují odesílání a přijímání UTF-8 a text v kódu Unicode, díky kterým jsou vhodné pro aplikace, které se týkají obousměrných jazyků. Webové klientské aplikace závisí na prohlížeče pro jeho uživatelské rozhraní, takže stupeň obousměrná podpora v webové aplikace závisí na tom, jak dobře webového prohlížeče podporuje tyto funkce obousměrné. V sadě Visual Studio můžete vytvářet aplikace s podporou arabský nebo hebrejský text, pořadí čtení zprava doleva, kódování souborů a nastavení místní jazykové verze. Další informace najdete v tématu [obousměrná podpora pro webové aplikace ASP.NET](https://msdn.microsoft.com/Library/5576f9b1-9b86-41ef-8354-092d366bcd03).

> [!NOTE]
> Aplikace konzoly nezahrnují text podpora obousměrných jazyků. Toto je v důsledku toho, jak funguje Windows pomocí konzolové aplikace.

## <a name="see-also"></a>Viz také:

- [Podpora obousměrných jazyků v sadě Visual Studio](use-bidirectional-languages.md)
- [Globalizace a lokalizace aplikací .NET](/dotnet/standard/globalization-localization/)
- [Prostředky v aplikacích .NET](/dotnet/framework/resources/)