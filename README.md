# Method Refinement

## Objective

The objective of Day 17 was to refine the selected classical enhancement method and identify the best validated parameter setting.

## Selected Method

CLAHE was selected for refinement because it was the strongest classical reference from the previous baseline evaluation.

## Parameters Tested

Four CLAHE parameter combinations were evaluated:

- CLAHE_1: Clip Limit = 1.0, Tile Grid Size = 8×8
- CLAHE_2: Clip Limit = 2.0, Tile Grid Size = 8×8
- CLAHE_3: Clip Limit = 3.0, Tile Grid Size = 8×8
- CLAHE_4: Clip Limit = 2.0, Tile Grid Size = 4×4

## Refinement Results

| Candidate | PSNR | SSIM | Edge F1 |
|---|---:|---:|---:|
| CLAHE_1 | 11.0273 | 0.4245 | 0.0581 |
| CLAHE_2 | 11.2504 | 0.4122 | 0.0642 |
| CLAHE_3 | 11.4000 | 0.3995 | 0.0688 |
| CLAHE_4 | 11.1650 | 0.4169 | 0.0635 |

## Observations

- CLAHE_3 achieved the highest PSNR of 11.40.
- CLAHE_3 also achieved the highest Edge F1 of 0.0688.
- CLAHE_1 achieved the highest SSIM of 0.4245.
- Increasing the clip limit improved PSNR and Edge F1 but reduced SSIM.
- The results show a trade-off between pixel similarity, structural similarity and edge preservation.

## Visual Artifact Check

The refined CLAHE output was visually compared with the input and target.

Observations:

- Visibility and local contrast were improved compared with the input.
- Important object boundaries were more visible.
- Some grain/noise was noticeable in the refined output.
- The refined output did not completely recover the target colour and fine details.

## Best Validated Candidate

**CLAHE_3**

Parameters:

- Clip Limit: 3.0
- Tile Grid Size: 8×8
- PSNR: 11.4000
- SSIM: 0.3995
- Edge F1: 0.0688

CLAHE_3 was selected as the best candidate based on its highest PSNR and Edge F1.

## Conclusion

Parameter refinement improved the classical CLAHE baseline. CLAHE_3 provided the strongest PSNR and edge-preservation performance, although the lower SSIM and visible grain indicate a quality trade-off.

The refined CLAHE_3 method will be retained as the best classical candidate for comparison with the learning-based approach.
