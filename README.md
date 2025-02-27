# Embiggened Annexolith Panels
A mod for [Esoterical](https://github.com/Esoterical)'s [Embiggened](https://github.com/Esoterical/PrinterMods/tree/main/Embiggened%20Monolith%20Panels) mod of [CloakedWayne](https://github.com/CloakedWayne)'s [Monolith panels](https://github.com/CloakedWayne/Monolith_Panels/tree/main) to include Annex-style quarter turn clips

My goal was to make the extra insulation thickness parametric, add optional heatset inserts all over the edges for mounting things, and replace the snap clips with Annex-style clips for a stronger hold to the frame. The split door from the original Monolith panels has not been converted - I would suggest a single piece door of some kind for higher temps.

Note that currently, **only the V2 is supported**. Trident support could be added if there's interest.

I have only printed the `350Bed 15.2Thick 6.6Seal 0.9Squish` version. Other combinations should work within reason, but beware of red features in the OnShape feature tree. Sanity check and test fit everything before committing to printing everything.

The source CAD is available [here on OnShape](https://cad.onshape.com/documents/7d4fb91dd4ba05e64f23a450/w/22745ee0f87958beb85178fe/e/81ea93f2c3178e66c3bc8df9?renderMode=0&uiState=67bfca6d314dbd1db3fbf2f7). Make your own copy to adjust the variables to match your printer.

## Instructions
### Printing
- As with the original Monolith panels, proper shrinkage compensation is critical. You'll probably be in for a bad time if you're off by even 0.1%. Be sure to average inside and outside measurements when calibrating.
- The STEP and STL files in the repo worked for my materials, but very likely will not work for you unless you buy the exact same products. I strongly suggest making your own copy of the CAD on OnShape and adjusting the variables to fit your materials. I used [1/2" PIR foam](https://www.lowes.com/pd/Johns-Manville-Common-0-5-in-x-4-ft-x-8-ft-Actual-0-5-in-x-4-ft-x-8-ft-AP-Foil-1-R-2-7-Faced-Polyisocyanurate-Foam-Board-Insulation/3851113), my stock LDO kit 3mm acrylic panels, and [1/4" D-profile silicone seals](https://www.amazon.com/dp/B0DLFV9V74?ref=ppx_yo2ov_dt_b_fed_asin_title).
- All STLs should be printed in the orientation that they come in with and without supports.
- The sides and back each use 2x`Horizontal Side`, 2x`V2 Vertical Side`, 4x`Corner`, 16x`Clip Shaft`, 16x`Clip Handle` and 16x`Clip Pin`
  - I completely deleted my exhaust port and did a full back panel, but you can probably omit the top horizontal piece to fit the stock exhaust.
  - I printed the `Clip Shaft`s with 6 walls for maximum strength, but less probably works too.
- The top is the same, except it uses 4x`Horizontal Side` and no vertical pieces.
- If you have things that you'd like to attach to the frame, insert standard Voron M3 heatset inserts where appropriate. Holes are dotted all along every piece.

### Clips
- Push a `Clip Shaft` through one of the holes, such that the part with the hole through it pokes out the side farthest from your frame. The shaft should snap into the hole once it's at the correct depth.
- Put a `Clip Handle` over the part with the hole that's poking out, such that the hole in the handle aligns with the one in the shaft. This is not designed to be a snap fit.
- Slide a `Clip Pin` through the hole in the handle with the tiny snap geometry facing away from the handle's flat side. The handle and pin should be oriented the same way that they come in in the slicer. This is designed to be a slight snap fit, and may require some force, depending on how the pieces were printed. Squeezing with needle nose pliers once the pin is started works well.
- Hold the base of the shaft against the side piece and give the clip a few rotations to wear the snap mechanism in and make sure everything fits correctly. Each 90 degree turn of the clip should take a little force and snap nicely into place at right angles.

From here, assembly is the same as the original [Monolith panels](https://github.com/CloakedWayne/Monolith_Panels/tree/main).

## CAD variables
- `TotalPanelThickness`: The total thickness of your base panel material. In my case, I used [1/2" PIR foam](https://www.lowes.com/pd/Johns-Manville-Common-0-5-in-x-4-ft-x-8-ft-Actual-0-5-in-x-4-ft-x-8-ft-AP-Foil-1-R-2-7-Faced-Polyisocyanurate-Foam-Board-Insulation/3851113) and my stock 3mm acrylic panels in a sandwich (with the acrylic on the outside, otherwise it will warp from the heat). I taped the two parts together along the edges with aluminum tape and measured the total thickness of the sandwich.
- `SealThickness`: The thickness of your sealing strip before it gets compressed. I used [1/4" D-profile silicone](https://www.amazon.com/dp/B0DLFV9V74?ref=ppx_yo2ov_dt_b_fed_asin_title). The stock foam that came with my LDO kit was absolutely unsuitable for high chamber temps.
- `SealSquish`: The amount that you want your sealing strips to get compressed after the clips are engaged. 0.9mm worked well for me.
- `BedSize`: The size of your printer's bed, e.g. 250, 300 or 350. Other sizes may work, but I did not test the CAD with them.
- `FloaterSize`: The total length of the floating piece that doesn't get attached to a corner piece. I used floaters to provide some extra pressure on edges where I had other things mounted (e.g. [Clicky-Clack](https://github.com/tanaes/whopping_Voron_mods/tree/main/clickyclacky_door) door hinges and latch)
