---
title: Lägg till information för kredithantering för kunder
description: I det här avsnittet beskrivs hur du lägger till information om kredithantering för en kund.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 919aa50136f02a44eb69146589496ad1284721f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447977"
---
# <a name="add-credit-management-information-for-customers"></a>Lägg till information för kredithantering för kunder

[!include [banner](../includes/banner.md)]

När du har ställt in parametrarna som styr kredithanteringen kan du lägga till mer information för varje kund. Dessa detaljer styr kredithanteringsprocesserna och innehåller också ytterligare information som hjälper medlemmar i inkassoteamet att hantera kunder.

## <a name="customer-information"></a>Kundinformation

Du kan lägga till kunduppgifter på snabbfliken **kredit och inkasso** på sidan **alla kunder** (**kundreskontra \> kunder \> alla kunder**).

1. Ställ in alternativet **obegränsad kreditgräns** till **ja** om kunden inte ska begränsas med några kreditgränstest.
2. Ange alternativet **exkludera från kredithantering** till **ja** för att utesluta kunden från de åtgärder som normalt inträffar under kredithanteringsprocesser.
3. Välj kredithanteringsgrupp för kunden.
4. Om du vill beräkna kreditgränsen i kundens valuta anger du kundens kreditgräns i fältet **kreditgräns** i kundens valuta. Kreditgränsen i företagsvalutan konverteras med hjälp av de valutakurser som definieras av växelkurstypen för kreditgräns som valts i parametrarna för kredithantering.
5. I fältet **senaste granskningsdatum** anger du det datum då kundens kreditgräns senast granskades av en kreditchef.
6. I fältet **nästa planerade granskningsdatum** anger du det datum då kunden är schemalagd för granskning och uppdatering av kredit.
7. I fältet **Berättigad kreditgräns** anger du den högsta kreditgränsen som kan tilldelas kunden, baserat på din granskning av kundens kredithistorik. Den berättigade kreditgränsen kan skilja sig från kreditgränsen som visas på snabbfliken **kredit och inkasso**.
8. I fältet **Berättigad valuta för kreditgränsen** anger du valutan för den berättigade kreditgränsen.
9. I fältet **Berättigat kreditgränsdatum** anger du det datum då den berättigade kreditgränsen skapades.
10. Ange kundens kreditkontostatus i fältet **kreditkontostatus**.
11. I fältet **Statusorsak** ange orsaken som är kopplad till kontostatus.
12. Ställ in alternativet **Med byrå** till **ja** för att ange att kunden för närvarande är tilldelad en kreditbyrå. Detta värde är endast för informationssyften. Det används inte i några kredithanteringsprocesser.
13. Ange alternativet **rubrik hållen** till **ja** om du vill ange att en rubrik hålls för företaget. Detta värde är endast för informationssyften. Det används inte i någon kredithanteringsprocess.
14. I fältet **Startdatum för företaget** ange datum då kunden först började göra affärer. Den här informationen används när riskresultat skapas.
15. I fältet **kund sedan** anger du det datum då de första transaktionerna bearbetades för kunden. Den här informationen används när riskresultat skapas.
16. Ange noteringar som kreditteamet kan använda för att ytterligare utvärdera kundens kreditvärdighet.

Observera att en del av informationen som visas på sidan **kund** skapas av en annan process:

- I fältet **utgångsdatum för kreditgräns** visas det datum då kreditgränsen förfaller. Om du inte anger det här fältet upphör kundens kreditgräns inte att gälla.
- I fältet **datum för kreditgräns** visas det datum då kreditgränsen skapades. Det här fältet uppdateras när kreditgränsen justeras.
- Tillfälliga kreditgränser åsidosätter kundens kreditgräns för en period. De används i stället för kreditgränsen för att beräkna den totala kreditgränsen. Den här informationen visas bara om det finns en aktiv kreditgräns. Du kan lägga till tillfälliga kreditgränser via kreditgränsjusteringar.
- Fältet **försäkring och garantier** visar det totala värdet av försäkringar och garantier som kan öka kreditgränsen för kunden.
- Fältet **Total kreditgräns** visar kundens slutgiltiga kreditgräns. Den totala kreditgränsen omfattar försäkringar och garantier samt tillfälliga kreditgränser.

## <a name="temporary-credit-limits"></a>Tillfälliga kreditgränser

Tillfälliga kreditgränser åsidosätter kundens kreditgränser för angiven period. Du kan lägga till tillfälliga kreditgränser via kreditgränsjusteringar. Kreditgränsjusteringar gör att kreditchefer uppdaterar kreditgränserna och utgångsdatum för en enskild kund, en grupp med kunder eller alla kunder via en bokföringsprocess.

Du kan skapa poster för kreditgränsjustering på sidan **kreditgränsjusteringar** (**kredithantering \> kreditgränsjusteringar \> kreditgränsjusteringar**).

## <a name="create-insurance-policies-and-guarantees"></a>Skapa försäkringsbrev och garantier

Du kan skapa en eller flera försäkringsbrev och garantier för varje kund. Du kan sedan använda dem för att beräkna den exponering som företaget har när det erbjuder kredit till en kund. Försäkringsbrev och garantier kan också ingå i kreditgränsen för en kund.

Du kan skapa försäkringsbrev och garantier på sidan **alla kunder** (**kundreskontra \> kunder \> alla kunder**). Välj en kund och sedan på åtgärdsfönstret på fliken **kredithantering** välj **försäkring och garantier**.

> [!NOTE]
> I följande procedur väljer du en försäkringsgivare eller borgenär i den globala adressboken. Innan du börjar med den här proceduren måste du därför se till att försäkringsgivare och borgenär har lagts till i den globala adressboken.

1. I fältet **identifierare** anger du **garanti** eller **försäkring**.
2. I fältet **garanti/försäkringstyp** väljer du en av de garanti- eller försäkringstyper som du har ställt in tidigare.
3. I fältet **försäkringsgivare/borgenär** väljer du en försäkringsgivare eller borgenär i den globala adressboken. 
4. Om du har valt **försäkring** i fältet **identifierare** väljer du i fältet **typ av policytäckning** en av de täckningstyper som du tidigare ställt in. Du kan inte välja en typ av policytäckning för en garanti.
5. I fältet **identifiering** anger du ID för policy. Detta ID är vanligtvis ett policynummer.
6. I fältet **Giltighet** anger du startdatum för försäkringsbrevet eller garantin.
7. I fältet **Utgång** anger du datum när försäkringsbrevet eller garantin. går ut.
8. I fältet **Värde** anger du värde för försäkringsbrevet eller garantin. Det här värdet är policyns fulla värde.
9. Välj valuta för policyvärde i fältet **valuta**. 
10. I fältet **Uppdatera kreditgräns** ange procent mellan **0** och **100**. Denna procentsats tillämpas på policyns värde och det resulterande beloppet kommer att användas för att öka kreditgränsen som används vid beräkningar av kreditgränser. Det beräknade värdet visas under **Total kreditgräns, försäkringar och garantier** på snabbfliken **kredit och inkasso** på sidan **kunder**.

    Här är ett exempel:

    - Kreditgränsen (A) är 100 000.
    - Policyvärde (B) är 50 000.
    - Procenten **Uppdatera kreditgräns** (C) är 50,00.
    
    I det här fallet är den effektiva kreditgränsen 125 000 (= A + \[B × C\]).

11. Markera kryssrutan **inkluderad i exponering** om du vill minska kreditgränsen som används i kreditgränsberäkningar med det fullständiga värdet av policyn. Om den här kryssrutan är markerad används det värde som beräknas när procenten **uppdatera kreditgräns** anges i kreditgränsberäkningar.

    Här är ett exempel:

    - Kreditgränsen (A) är 100 000.
    - Policyvärde (B) är 50 000.
    - Procenten **Uppdatera kreditgräns** (C) är 50,00.

    I det här fallet är den effektiva kreditgränsen 125 000 (= A + \[B × C\]).
    
    Om du däremot markerar kryssrutan **inkluderad i exponering** tas värdet **Uppdatera kreditgräns** på 50 000 (= 50,00 procent av 100 000) bort och exponeringsvärdet är 75 000 (= A + \[B × C\] – B).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]