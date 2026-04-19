# CASS

**CASS: Nvidia to AMD Transpilation with Data, Models, and Benchmark**
*Accepted at ACL 2026 Main Conference.*

## Links

- [Paper](https://arxiv.org/abs/2505.16968)
- [Dataset](https://huggingface.co/datasets/MBZUAI/cass)
- [Benchmark](https://huggingface.co/datasets/MBZUAI/cass-bench)

## Website

The project page lives in `index.html` (plain static site). All figures live under
`static/images/` — paper figures cropped from the ACL camera-ready PDF are in
`static/images/paper_figs/`.

## Changelog

### 2026-04-19 — Website sync with ACL 2026 camera-ready

Brought `index.html` in line with the ACL 2026 version of the paper.

- **Added** ACL 2026 Main Conference badge under the title.
- **Updated** author list to 8 authors: added Mukul Ranjan and Arina Kharlamova
  as equal contributors.
- **Updated** headline numbers across abstract, contributions, and result tables:
  - Dataset size: 70k → **60,694 aligned pairs** (from ~66k collected)
  - GPU domains: 16 → **18**
  - CASS-Bench: 40 samples → **369 samples**
  - CASS-7B source accuracy: 95% → **88.17%**
  - CASS-7B assembly accuracy: 37.5% → **69.11%** (with 90.24% compile rate)
  - Ablation numbers refreshed (Stack 79.67/48.24 → +Synth → +OpenCL → +RoPE
    88.17/69.11).
- **Rebuilt** results table with the ACL camera-ready Table 3 (includes GPT-5.1,
  Claude-Haiku-4.5, Gemini-2.5-Pro, DeepSeek-Coder-V2-Lite, etc.) and separate
  Test Acc. / Compile Rate columns for both assembly and source.
- **Added** new section **"CUDA vs. HIP Compiler Stacks"** using Figure 2 from
  the paper to explain why cross-architecture translation is non-trivial.
- **Added** new section **"Analysis"** containing:
  - Figure 7 — effect of input length on assembly translation
  - Figure 8 — assembly-level failures across categories
- **Replaced** the CASS-Bench domain figure with Figure 3 from the paper
  (coverage across dataset and benchmark: category / domain / verbosity).
- **Added** Figure 6 (CUDA↔HIP CHRF similarity) under the Results section.
- **Replaced** the teaser figure with Figure 1 from the ACL camera-ready.
- **Fixed** Windows-style backslash paths in image `src` attributes
  (`static\images\...` → `static/images/...`) so the site renders on Linux
  hosts and GitHub Pages.
- **Added** six new paper figures under `static/images/paper_figs/`:
  `fig1_pipeline.png`, `fig2_stacks.png`, `fig3_coverage.png`,
  `fig6_chrf.png`, `fig7_inputlen.png`, `fig8_failures.png`.
- **Regenerated** all paper figures from the ACL source zip
  (`_acl25__cass.zip` → original `assets/*.pdf`) at 220 DPI, replacing the
  earlier PDF-page crops that had caption text bleeding in.
- **Split** Figure 3 into its three source panels
  (`fig3a_category.png`, `fig3b_domains.png`, `fig3c_loc.png`) and rendered
  them as a 3-column grid with a new `.three-col-figs` CSS rule.
- **Removed** the old cropped `main_cass-distribution.drawio_page-0001.jpg`
  from the Dataset Composition section (duplicated by Fig 3b).
- **Added** per-figure captions (`.figure-caption` CSS class) under every
  figure: Fig 1 pipeline, Fig 2 compiler stacks, Fig 3 coverage, Fig 6
  CHRF, Fig 7 input length, Fig 8 failures by category.

## Citation

```bibtex
@misc{heakl2025cassnvidiaamdtranspilation,
 title={CASS: Nvidia to AMD Transpilation with Data, Models, and Benchmark},
 author={Ahmed Heakl and Gustavo Bertolo Stahl and Sarim Hashmi and Seung Hun Eddie Han and Mukul Ranjan and Arina Kharlamova and Salman Khan and Abdulrahman Mahmoud},
 year={2025},
 eprint={2505.16968},
 archivePrefix={arXiv},
 primaryClass={cs.AR},
 url={https://arxiv.org/abs/2505.16968},
}
```