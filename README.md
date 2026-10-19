# Google Hash Code Datasets

A curated collection of official competition instances, community-created datasets, and synthetic benchmarks for the 21 optimization problems of the [Google Hash Code](https://github.com/pierreavn/google-hashcode-archive) competition (2014–2022).

## Overview

| Problem | Edition / Round | Official instances | Additional datasets | Total |
|---|---|:---:|---|:---:|
| `assembling_smartphones` | 2020 Final | 6 | – | 6 |
| `book_scanning` | 2020 Qualification | 6 | 45 real-world + 139 synthetic + 135 seed-based [[ILSBookScanning]](#ref-ilsbookscanning) | 325 |
| `city_plan` | 2018 Final | 6 | – | 6 |
| `compiling_google` | 2019 Final | 6 | – | 6 |
| `delivery` | 2016 Qualification | 3 | 80+ simulated [[Yadav2017]](#ref-yadav2017) ⚠️ | 83+ |
| `even_more_pizza` | 2021 Practice | 5 | – | 5 |
| `loon` | 2015 Final | 1 | – | 1 |
| `mentorship_and_teamwork` | 2022 Qualification | 6 | – | 6 |
| `more_pizza` | 2020 Practice | 5 | – | 5 |
| `one_pizza` | 2022 Practice | 5 | – | 5 |
| `optimize_a_data_center` | 2015 Qualification | 1 | – | 1 |
| `photo_slideshow` | 2019 Qualification | 5 | 45 synthetic + 10 real-life [[Arbneshi2023]](#ref-arbneshi2023) ⚠️ | 60 |
| `pizza` | 2017 Practice | 4 | – | 4 |
| `router_placement` | 2017 Final | 4 | – | 4 |
| `santa_tracker` | 2022 Final | 6 | – | 6 |
| `satellites` | 2016 Final | 4 | – | 4 |
| `self_driving_rides` | 2018 Qualification | 5 | – | 5 |
| `software_engineering_at_scale` | 2021 Final | 6 | – | 6 |
| `streaming_videos` | 2017 Qualification | 4 | – | 4 |
| `street_view_routing` | 2014 Final | 1 | – | 1 |
| `traffic_signaling` | 2021 Qualification | 6 | 43 synthetic [[Misini2025]](#ref-misini2025) | 49 |

⚠️ = described in the literature but not publicly available (see the problem section for details).

**Official instances** are the input files released by Google for each round, archived in [[HashCodeArchive]](#ref-archive). The count includes the small example file where one was distributed as a separate input. Most research papers exclude the example file, so their benchmark sets are one instance smaller.

---

## Problems with additional datasets

### `book_scanning` (Hash Code 2020, Qualification)

**Download:** https://github.com/dritonalija/ils_book_scanning/tree/main/input

| Dataset | Folder | Instances | Reference |
|---|---|:---:|---|
| Official Google instances | `google_hashcode/` | 6 (5 in the folder, without the example) | [[HashCodeArchive]](#ref-archive) |
| Real-world | `real_world/` | 45 | [[ILSBookScanning]](#ref-ilsbookscanning), [[Alija2025]](#ref-alija2025) |
| Synthetic | `synthetic/` | 139 | [[ILSBookScanning]](#ref-ilsbookscanning) |
| Seed-based | `seed_based/` | 135 | [[ILSBookScanning]](#ref-ilsbookscanning) |

- **Official:** `a_example`, `b_read_on`, `c_incunabula`, `d_tough_choices`, `e_so_many_books`, `f_libraries_of_the_world`. They range from 78,600 to 100,000 books, 100 to 30,000 libraries, and 200 to 100,000 days.
- **Real-world:** 45 instances generated with the Book Scanning Instance Generator, designed to reflect real-world scanning scenarios. The 15 synthetic instances evaluated in [[Alija2025]](#ref-alija2025) are a subset of this set. Naming convention: `B<books>_L<libraries>_D<days>`.
- **Synthetic:** a larger pool of 139 generated instances, used for training and evaluation.
- **Seed-based:** 135 reproducible instances derived from the official seed files. They combine 5 seed families (`b`–`f`) and 10 cross-bred families (`bc`, `bd`, …, `ef`) at 3 scale levels and 3 tightness levels. Naming convention: `<family>_<scale>x_<tightness>t`, for example `ce_075x_012t` (scores from seed `c`, structure from seed `e`, scale 0.75, tightness 0.12).

<details>
<summary>The 15 real-world instances used in Alija et al. (2025)</summary>

`B300_L11_D20`, `B500_L14_D18`, `B750_L20_D14`, `B1k_L18_D17`, `B1.5k_L20_D40`, `B2.5k_L25_D50`, `B4k_L30_D60`, `B5k_L90_D21`, `B6k_L35_D70`, `B9k_L40_D80`, `B50k_L400_D28`, `B60k_L70_D140`, `B90k_L850_D21`, `B95k_L2k_D28`, `B100k_L600_D28`

</details>

[[Alija2025]](#ref-alija2025) evaluates ILS and GA on 20 instances (the 5 official instances without the example, plus the 15 above). It reports upper bounds, MILP results, and best-known values.

### `delivery` (Hash Code 2016, Qualification — Drone Delivery)

| Dataset | Instances | Reference | Availability |
|---|:---:|---|---|
| Official Google instances | 3 | [[HashCodeArchive]](#ref-archive) | Public |
| Simulated instances | 80+ (exact number not reported) | [[Yadav2017]](#ref-yadav2017) | ⚠️ Not published |

- **Official:** `busy_day` (1,250 orders, 10 warehouses), `mother_of_all_warehouses` (800 customers, 1 warehouse), `redundancy` (1,000 orders, 16 warehouses).
- **Simulated:** more than 80 instances with 15, 30, and 45 customers on a 400-square grid, with randomly placed warehouses. They were generated following the scheme of Murray and Chu [[Murray2015]](#ref-murray2015). The paper's dataset link (https://tinyurl.com/ydg9cfp5) redirects to Google's 2016 problem statement, which is no longer online. The simulated instances have not been published.

### `photo_slideshow` (Hash Code 2019, Qualification)

| Dataset | Instances | Reference | Availability |
|---|:---:|---|---|
| Official Google instances | 5 | [[HashCodeArchive]](#ref-archive), [[Google2019]](#ref-google2019) | Public |
| Synthetic instances | 45 | [[Arbneshi2023]](#ref-arbneshi2023) | ⚠️ Not published |
| Real-life instances | 10 | [[Arbneshi2023]](#ref-arbneshi2023) | ⚠️ Not published |

- **Official:** `a_example`, `b_lovely_landscapes`, `c_memorable_moments`, `d_pet_pictures`, `e_shiny_selfies`. They contain 1,000 to 90,000 photos with an average of 9.4 to 19.1 tags per photo.
- **Synthetic:** 50 to 100,000 photos with about 15 tags per photo. Naming convention: `P<photos>_H<horizontal>_V<vertical>`.
- **Real-life:** about 97 photos per instance on average, with about 4 tags per photo. The photos come from [Unsplash](https://unsplash.com/), and the tags were extracted with the TensorFlow Object Detection API.
- Both sets were produced with the web generator at [slideshow.instance.generator.erzen.tk](https://slideshow.instance.generator.erzen.tk/). The instance files themselves are not included with the paper or its code repository ([labeatarbneshi/photo-slideshow](https://github.com/labeatarbneshi/photo-slideshow)).

<details>
<summary>List of the 45 synthetic instances</summary>

- **P50:** `P50_H10_V40`, `P50_H25_V25`, `P50_H40_V10`, `P50_H0_V50`, `P50_H50_V0`
- **P75:** `P75_H0_V75`, `P75_H20_V55`, `P75_H40_V35`, `P75_H55_V20`, `P75_H75_V0`
- **P100:** `P100_H0_V100`, `P100_H100_V0`, `P100_H30_V70`, `P100_H50_V50`, `P100_H70_V30`
- **P500:** `P500_H0_V500`, `P500_H100_V400`, `P500_H250_V250`, `P500_H400_V100`, `P500_H500_V0`
- **P1k:** `P1k_H0_V1k`, `P1k_H100_V900`, `P1k_H1k_V0`, `P1k_H500_V500`, `P1k_H900_V100`
- **P5k:** `P5k_H0_V5k`, `P5k_H1k_V4k`, `P5k_H2.5k_V2.5k`, `P5k_H4k_V1k`, `P5k_H5k_V0`
- **P10k:** `P10k_H0_V10k`, `P10k_H10k_V0`, `P10k_H1k_V9k`, `P10k_H5k_V5k`, `P10k_H9k_V1k`
- **P50k:** `P50k_H0_V50k`, `P50k_H10k_V40k`, `P50k_H25k_V25k`, `P50k_H40k_V10k`, `P50k_H50k_V0`
- **P100k:** `P100k_H0_V100k`, `P100k_H100k_V0`, `P100k_H10k_V90k`, `P100k_H50k_V50k`, `P100k_H90k_V10k`

> Note: Table 2 of [[Arbneshi2023]](#ref-arbneshi2023) omits `P50_H0_V50` and lists `P50k_H0_V50k` twice. The list above follows Table 4 of the same paper, which reports results for all 45 instances.

</details>

<details>
<summary>List of the 10 real-life instances</summary>

`Animals`, `Arts & Culture`, `Athletics`, `Business & Work`, `Film`, `Food & Drinks`, `Health & Wellness`, `Nature`, `People`, `Travel`

</details>

[[Arbneshi2023]](#ref-arbneshi2023) evaluates its methods on 59 instances (4 official without the example, 45 synthetic, and 10 real-life). It reports ILP upper bounds for the smaller instances.

### `traffic_signaling` (Hash Code 2021, Qualification)

**Download:** https://www.kaggle.com/datasets/uranla/hash-code-2021-traffic-signaling-synthetic-set

| Dataset | Instances | Reference |
|---|:---:|---|
| Official Google instances | 6 | [[HashCodeArchive]](#ref-archive) |
| Extended synthetic instances | 43 | [[Misini2025]](#ref-misini2025), [[Lajci2024]](#ref-lajci2024), [[Limani2024]](#ref-limani2024) |

- **Official:** `a` (example), `b_by_the_ocean`, `c_checkmate`, `d_daily_commute`, `e_etoile`, `f_forever_jammed`. They range from 500 to 10,000 intersections, 998 to 95,928 streets, and 1,000 cars each. Some works rename them with the synthetic convention, for example `I7073_S9102_C1000` for B and `I1662_S10000_C1000` for F.
- **Synthetic:** 70 to 12,000 intersections, 210 to 57,155 streets, 57 to 2,000 cars, and simulation times from 70 to 10,000 seconds. They were generated with the web tool at [trafficsignaling.instance.generator.erzen.tk](https://trafficsignaling.instance.generator.erzen.tk/). Naming convention: `I<intersections>_S<streets>_C<cars>`.

<details>
<summary>List of the 43 synthetic instances</summary>

`I70_S210_C200`, `I80_S240_C300`, `I80_S480_C600`, `I90_S360_C400`, `I99_S399_C400`, `I100_S400_C600`, `I100_S500_C500`, `I100_S600_C153`, `I110_S330_C450`, `I120_S480_C500`, `I120_S720_C400`, `I150_S45150_C100`, `I155_S57155_C300`, `I180_S1080_C800`, `I200_S1000_C400`, `I200_S1000_C550`, `I200_S4200_C400`, `I200_S17200_C1000`, `I220_S660_C430`, `I220_S1100_C558`, `I241_S43241_C158`, `I300_S900_C500`, `I300_S1500_C469`, `I400_S2400_C944`, `I444_S1776_C666`, `I500_S2000_C315`, `I600_S3000_C332`, `I2000_S6000_C376`, `I2000_S12000_C57`, `I2500_S10000_C306`, `I2999_S17994_C103`, `I3000_S12000_C407`, `I3000_S15000_C316`, `I3000_S18000_C227`, `I3333_S13332_C428`, `I4000_S12000_C161`, `I4000_S12000_C387`, `I4000_S12000_C397`, `I4000_S20000_C309`, `I4000_S24000_C401`, `I9000_S36000_C1500`, `I10000_S30000_C1200`, `I12000_S36000_C2000`

</details>

All three works evaluate on the same 48-instance benchmark (5 official without the example, plus 43 synthetic). They report upper bounds and compare against Shporer's greedy solver [[Shporer2021]](#ref-shporer2021).

---

## Problems with only official instances

No additional datasets were found in the literature for these problems. All instances come from [[HashCodeArchive]](#ref-archive).

| Problem | Round | Instances | Input files |
|---|---|:---:|---|
| `assembling_smartphones` | 2020 Final | 6 | `a_example`, `b_single_arm`, `c_few_arms`, `d_tight_schedule`, `e_dense_workspace`, `f_decentralized` |
| `city_plan` | 2018 Final | 6 | `a_example`, `b_short_walk`, `c_going_green`, `d_wide_selection`, `e_precise_fit`, `f_different_footprints` |
| `compiling_google` | 2019 Final | 6 | `a_example`, `b_narrow`, `c_urgent`, `d_typical`, `e_intriguing`, `f_big` |
| `even_more_pizza` | 2021 Practice | 5 | `a_example`, `b_little_bit_of_everything`, `c_many_ingredients`, `d_many_pizzas`, `e_many_teams` |
| `loon` | 2015 Final | 1 | single input file |
| `mentorship_and_teamwork` | 2022 Qualification | 6 | `a_an_example`, `b_better_start_small`, `c_collaboration`, `d_dense_schedule`, `e_exceptional_skills`, `f_find_great_mentors` |
| `more_pizza` | 2020 Practice | 5 | `a_example`, `b_small`, `c_medium`, `d_quite_big`, `e_also_big` |
| `one_pizza` | 2022 Practice | 5 | `a_an_example`, `b_basic`, `c_coarse`, `d_difficult`, `e_elaborate` |
| `optimize_a_data_center` | 2015 Qualification | 1 | `dc.in` |
| `pizza` | 2017 Practice | 4 | `example`, `small`, `medium`, `big` |
| `router_placement` | 2017 Final | 4 | `charleston_road`, `lets_go_higher`, `opera`, `rue_de_londres` |
| `santa_tracker` | 2022 Final | 6 | `a_an_example`, `b_better_hurry`, `c_carousel`, `d_decorated_houses`, `e_excellent_weather`, `f_festive_flyover` |
| `satellites` | 2016 Final | 4 | `constellation`, `forever_alone`, `overlap`, `weekend` |
| `self_driving_rides` | 2018 Qualification | 5 | `a_example`, `b_should_be_easy`, `c_no_hurry`, `d_metropolis`, `e_high_bonus` |
| `software_engineering_at_scale` | 2021 Final | 6 | inputs A–F |
| `streaming_videos` | 2017 Qualification | 4 | `kittens`, `me_at_the_zoo`, `trending_today`, `videos_worth_spreading` |
| `street_view_routing` | 2014 Final | 1 | `paris_54000` |

---

## References

- <a id="ref-archive"></a>**[HashCodeArchive]** P. Avnimelech (pierreavn). *Google Hash Code Archive (Problems & Scoreboards).* https://github.com/pierreavn/google-hashcode-archive
- <a id="ref-google2019"></a>**[Google2019]** Google. *Hash Code 2019 Qualification Round: Photo slideshow (problem statement).* https://storage.googleapis.com/coding-competitions.appspot.com/HC/2019/hashcode2019_qualification_task.pdf
- <a id="ref-ilsbookscanning"></a>**[ILSBookScanning]** D. Alija et al. *Iterated Local Search for Book Scanning — input datasets.* https://github.com/dritonalija/ils_book_scanning/tree/main/input
- <a id="ref-yadav2017"></a>**[Yadav2017]** V. Yadav, A. Narasimhamurthy. "A heuristics based approach for optimizing delivery schedule of an Unmanned Aerial Vehicle (Drone) based delivery system." IEEE, 2017.
- <a id="ref-murray2015"></a>**[Murray2015]** C. C. Murray, A. G. Chu. "The flying sidekick traveling salesman problem: Optimization of drone-assisted parcel delivery." *Transportation Research Part C*, 54:86–109, 2015.
- <a id="ref-arbneshi2023"></a>**[Arbneshi2023]** L. Arbneshi, K. Sylejmani, N. Halili, E. Krasniqi. "Automated Slideshow Design from a Set of Photos Based on a Hybrid Metaheuristic Approach." *Operations Research Forum*, 4:75, 2023. https://doi.org/10.1007/s43069-023-00261-0
- <a id="ref-alija2025"></a>**[Alija2025]** D. Alija, M. Kryeziu, E. Hoda, L. Islami, L. Mustafa, Y. Berisha, K. Sylejmani, A. Ahmeti, L. Arbneshi. "Optimization of the Book Scanning Problem via Iterated Local Search and Genetic Algorithms." *6th Int. Conf. on Recent Trends and Applications in Computer Sciences and Information Technologies (RTA-CSIT)*, Tirana, Albania, 2025. CEUR Workshop Proceedings, Vol-4044.
- <a id="ref-misini2025"></a>**[Misini2025]** E. Misini, U. Lajçi, K. Sylejmani, A. Limani, F. Gashi, L. Kurtaj, A. Ahmeti, E. Krasniqi. "Solving the traffic signaling problem using the iterated local search metaheuristic." *Discover Applied Sciences*, 7:792, 2025. https://doi.org/10.1007/s42452-025-07054-6
- <a id="ref-lajci2024"></a>**[Lajci2024]** U. Lajçi, A. Limani, E. Misini, F. Gashi, K. Sylejmani, A. Ahmeti. "Metaheuristic techniques for automated traffic light scheduling to minimize commute time." *Proc. 14th Int. Conf. on the Practice and Theory of Automated Timetabling (PATAT 2024)*, pp. 334–337.
- <a id="ref-limani2024"></a>**[Limani2024]** A. Limani, K. Sylejmani, U. Lajçi, E. Misini, E. Krasniqi, B. Krasniqi. "Smart Traffic Signal Optimization with an Artificial Bee Colony Algorithm." *Proc. 16th Int. Conf. on Agents and Artificial Intelligence (ICAART)*, Rome, Italy, 2024.
- <a id="ref-shporer2021"></a>**[Shporer2021]** S. Shporer. *Solver for traffic signaling problem of Google Hash Code competition – qualification round 2021.* https://github.com/sagishporer/hashcode-2021-qualification

## License

Released under the MIT License. The original Hash Code problem statements and instances belong to Google. Derived datasets belong to their respective authors; please cite the corresponding papers when you use them.
