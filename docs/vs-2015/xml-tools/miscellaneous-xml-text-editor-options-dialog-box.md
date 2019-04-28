---
title: Různé, XML, textový Editor, dialogové okno Možnosti | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: fd3fff31-cddc-422d-a2f0-a5a1ef492afd
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: edf638420ac41d6ad6f7ebf5e20ab5d78d1c7b3d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435370"
---
# <a name="miscellaneous-xml-text-editor-options-dialog-box"></a>Různé, XML, Textový editor, dialogové okno Možnosti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Toto dialogové okno umožňuje změnit nastavení automatického dokončování a schéma pro Editor XML. Můžete přistupovat **možnosti** dialogové **nástroje** nabídky.  
  
> [!NOTE]
> Tato nastavení jsou k dispozici, když vyberete **textový Editor** složku, **XML** složky a pak **různé** možnost **možnosti** dialogové okno.  
  
## <a name="auto-insert"></a>Automatické vkládání  
 **Zavřít značky**  
 Pokud je nastavení automatického doplňování je zaškrtnuto, editoru automaticky přidá koncovou značku po zadání pravé ostré závorky (>) zavřete počáteční značku, pokud už značka není uzavřená. Toto je výchozí chování.  
  
 Dokončení prázdný element není závislý na nastavení automatického doplňování. Můžete vždy automatické dokončování prázdný element tak, že zadáte zpětné lomítko (/).  
  
 **Uvozovky atributu**  
 Při vytváření atributy ve formátu XML, editor vloží `=" "` znaků a pozice kurzoru (^) do dvojitých uvozovek.  
  
 Ve výchozím nastavení je zaškrtnuto.  
  
 **Deklarace Namespace**  
 Editor automaticky vloží deklarace oboru názvů, bez ohledu na to se v případě potřeby zapíná.  
  
 Ve výchozím nastavení je zaškrtnuto.  
  
 **Jiné značky (komentáře, CDATA)**  
 Komentáře, CDATA, DOCTYPE, pokyny pro zpracování a další značky jsou automaticky dokončují.  
  
 Ve výchozím nastavení je zaškrtnuto.  
  
## <a name="network"></a>Síť  
 **Automaticky stahovat specifikace DTD a schémata**  
 Schémata a definice typu dokumentu (DTD) se automaticky stáhnou z umístění protokolu HTTP. Tato funkce používá System.Net s detekcí automaticky proxy server povolený.  
  
 Ve výchozím nastavení je zaškrtnuto.  
  
## <a name="outlining"></a>Sbalování  
 **Po otevření souborů vstoupit do režimu sbalování**  
 Při otevření souboru se změní na funkci sbalování.  
  
 Ve výchozím nastavení je zaškrtnuto.  
  
## <a name="caching"></a>Ukládání do mezipaměti  
 **Schémata**  
 Určuje umístění mezipaměti schémat. Tlačítko Procházet (**...** ) otevře **Procházet adresář** dialogové okno na aktuální umístění mezipaměti schémat. Můžete vybrat jiný adresář, nebo můžete vybrat složku v dialogovém okně klikněte pravým tlačítkem a zvolte **otevřít** zjistíte Novinky v adresáři.  
  
## <a name="see-also"></a>Viz také  
 [Vlastnosti dokumentu XML, okno Vlastnosti](../xml-tools/xml-document-properties-properties-window.md)   
 [Součásti editoru XML](../xml-tools/xml-editor-components.md)
