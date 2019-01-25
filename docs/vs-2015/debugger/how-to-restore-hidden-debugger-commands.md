---
title: 'Postupy: Obnovení skrytých příkazů ladicího programu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, restoring commands
- debugging [Visual Studio], restoring commands
- commands, debugger
ms.assetid: 76ac9b77-f536-43b5-a9fc-984854b1c566
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 83a685b0dfc9b4f260d082230a5b58dcb025eff4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54779508"
---
# <a name="how-to-restore-hidden-debugger-commands"></a>Postupy: Obnovení skrytých příkazů ladicího programu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při nastavování aplikace Visual Studio, zobrazí se výzva k výběru sada výchozích nastavení IDE pro primární programovací jazyk. Výchozí nastavení rozhraní IDE pro některé jazyky mohou skrývat určité příkazy ladicího programu.  
  
 Pokud chcete použít funkci ladicí program, který je skryt výchozího nastavení IDE, můžete přidat příkaz zpět do nabídky pomocí následujícího postupu.  
  
### <a name="to-restore-hidden-debugger-commands"></a>K obnovení skrytých příkazů ladicího programu  
  
1.  S projektem otevřeným v **nástroje** nabídky, klikněte na tlačítko **vlastní**.  
  
2.  V **vlastní** dialogové okno, klikněte na tlačítko **příkazy** kartu.  
  
3.  V **nabídek:** rozevíracího seznamu, vyberte **ladění** nabídky, která má obsahovat příkaz obnovený.  
  
4.  Klikněte na tlačítko **přidat příkaz...** tlačítko.  
  
5.  V **přidat příkaz** , vyberte příkaz, který chcete přidat a klikněte na tlačítko **OK**.  
  
6.  Opakujte předchozí krok a přidejte další příkaz.  
  
7.  Klikněte na tlačítko **Zavřít** po dokončení přidání komentářů k nabídce.  
  
    > [!WARNING]
    >  Některé položky nabídky se zobrazí, pouze když ladicí program v konkrétní režimy, jako je například režimu běhu nebo režimu pozastavení. Položka, kterou jste přidali proto nemusí být ihned po dokončení těchto kroků.  
  
## <a name="restoring-commands-not-available-from-the-customize-dialog-box"></a>Obnovení příkazů není k dispozici z dialogového okna Přizpůsobit  
 Některé příkazy, zejména těch, které jsou součástí hierarchické nabídky, nelze obnovit z **vlastní** dialogové okno. Chcete-li obnovit tyto příkazy, je nutné naimportovat nové kolekce nastavení prostředí IDE.  
  
#### <a name="to-import-new-ide-settings"></a>Chcete-li importovat nové nastavení prostředí IDE  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **nastavení importu a exportu**.  
  
2.  Na **Vítejte Průvodci importem a exportem nastavení** klikněte na **importovat vybrané nastavení prostředí**a potom klikněte na tlačítko **Další**.  
  
3.  Na **uložit aktuální nastavení** stránce, rozhodněte, jestli se mají uložit stávající nastavení a klikněte na **Další**.  
  
4.  Na **zvolte kolekce nastavení chcete importovat** stránce v části **výchozí nastavení** složky, zvolte kolekci nastavení pro vývoj, který obsahuje příkazy, které chcete použít. Pokud si nejste jisti kterou kolekci zvolte, zkuste **obecným vývojovým nastavením** nebo **Visual C++ – vývojové nastavení**, které poskytují největší příkazy ladicího programu.  
  
5.  Klikněte na **Další**.  
  
6.  Na **zvolte nastavení pro import** stránce v části **možnosti**, ujistěte se, že **ladění** zaškrtnuto. Zrušte zaškrtnutí ostatních políček, pokud chcete importovat tato nastavení také.  
  
7.  Klikněte na tlačítko **Dokončit**.  
  
8.  Na **úplný Import** stránky, zkontrolujte všechny chyby spojené s obnovením vašeho nastavení v části **podrobnosti**.  
  
9. Klikněte na **Zavřít**.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)
