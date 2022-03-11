// Copyright (C) Pakyman Prod. 2020. All Rights Reserved.

#include "Graph/ASMTransition.h"
#include "AGSCondition.h"
#include <Kismet/GameplayStatics.h>

bool UASMTransition::VerifyTransitionConditions()  {
  
    for ( UAGSCondition *cond : ActivationConditions) {
   
      if (cond && cond->Verify(UGameplayStatics::GetPlayerController(this, 0))) {
        continue;
      } 
      else {     
          return false;   
      }
  
  }
  return true;
}
