#include "AchievementWrapper.h"
#include "AchievementManager.hh"

extern "C" {
    void achievement_wrapper_init(){
        auto& manager = AchievementManager::GetInstance();
        manager.Init();
    }
}
