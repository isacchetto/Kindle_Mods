local userpatch = require("userpatch")
local logger = require("logger")
local VerticalSpan = require("ui/widget/verticalspan")

local function patchMosaicMenu(plugin)
    
    local ptutil = require("ptutil")
    
    local original_mediumBlackLine = ptutil.mediumBlackLine
    local original_thinGrayLine = ptutil.thinGrayLine
    
    ptutil.mediumBlackLine = function(width)
        return VerticalSpan:new { width = 0 }
    end
    
    ptutil.thinGrayLine = function(width)
        return ptutil.thinWhiteLine(width)
    end
    
    logger.info("MosaicMenu patched: ptutil line functions overridden to remove borders")
end

userpatch.registerPatchPluginFunc("coverbrowser", patchMosaicMenu)