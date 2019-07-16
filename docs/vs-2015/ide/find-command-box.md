---
title: Pole najít / příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.findcommandbox
helpviewer_keywords:
- Find/Command box
ms.assetid: c81736dd-7a26-4e11-95c8-c2a2e56d7a41
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b8bddc27eb4a59b65796c7837ae4561e5d56a5d5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68160659"
---
# <a name="findcommand-box"></a>Pole Najít/příkaz
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete hledat text a spustit příkazy sady Visual Studio z **najít/příkaz** pole. **Najít/příkaz** pole je stále k dispozici jako ovládací prvek panelu nástrojů, ale už není ve výchozím nastavení viditelný. Můžete zobrazit **najít/příkaz** pole výběrem **přidat nebo odebrat tlačítka** na **standardní** nástrojů a následným výběrem možnosti **najít**.  
  
 Ke spuštění [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] příkaz, musí se znaménkem větší než (>).  
  
 **Najít/příkaz** pole zachová poslední 20 položek zadaných a zobrazí je v rozevíracím seznamu. Můžete procházet seznam výběrem klávesy se šipkami.  
  
 ![Najít&#47;příkaz pole](../ide/media/findcommandbox.png "FindCommandBox")  
Pole Najít/příkaz  
  
## <a name="searching-for-text"></a>Hledání textu  
 Ve výchozím nastavení při zadávání textu **najít/příkaz** pole a klikněte na tlačítko ENTER klíče, Visual Studio vyhledá aktuální okno dokumentu nebo nástroj pomocí možností, které jsou uvedeny v **najít v souborech**dialogové okno. Další informace najdete v tématu [hledání a nahrazení textu](../ide/finding-and-replacing-text.md).  
  
## <a name="entering-commands"></a>Zadávání příkazů  
 Použít **najít/příkaz** pole vydat jediného [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] příkaz % $n nebo alias místo Hledat text, zadejte [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] příkaz začíná symbol větší než (>). Příklad:  
  
```  
>File.NewFile c:\temp\MyFile /t:"General\Text File"  
```  
  
 Případně také můžete příkazové okno k zadání a spuštění jednoho nebo více příkazů. Některé příkazy nebo aliasy lze zadat a spustit samostatně; ostatní vyžadovala trojnásobnou investici argumenty v syntaxi. Seznam příkazů, které mají argumenty najdete v tématu [příkazy sady Visual Studio](../ide/reference/visual-studio-commands.md).  
  
## <a name="escape-characters"></a>Řídicí znaky  
 Znak stříšky (^) v příkazovém řádku znamená, že znak, který bezprostředně následují je interpretován doslovně a ne jako řídicí znak. To slouží k vložení uvozovek ("), mezer, úvodních lomítek, střížek nebo jakýmikoli literálními znaky parametru nebo hodnotě switch s výjimkou názvů switchů. Například  
  
```  
>Edit.Find ^^t /regex  
```  
  
 Stříška funguje stejně, ať už se jedná o vnitřní nebo vnější uvozovky. Pokud poslední znak na řádku stříška, je ignorován.  
  
## <a name="see-also"></a>Viz také  
 [Okno příkazového řádku](../ide/reference/command-window.md)   
 [Hledání a nahrazení textu](../ide/finding-and-replacing-text.md)
