Guide how to link GitHub repositories with Zenodo to obtain a DOI
======

We originally created this guide to provide hints on how to deal with the rules imposed by our grant agency, the National Science Center (NCN), Poland, 
regarding publishing in Open Access, GitHub repositories and the need for permanent DOIs. But don't hesitate to use it if you need to link your GitHub repositories to Zenodo for DOI for any other purpose.


- [How to](#how-to)
  - [Additional remarks and optional steps:](#additional-remarks-and-optional-steps)
- [Unanswered questions](#unanswered-questions)
- [Discussion](#discussion)



[![DOI](https://zenodo.org/badge/584345819.svg)](https://zenodo.org/badge/latestdoi/584345819) [![cffconvert](https://github.com/filipsPL/NCN-github-OA/actions/workflows/cffconvert.yml/badge.svg)](https://github.com/filipsPL/NCN-github-OA/actions/workflows/cffconvert.yml)


**Notice of Non-Affiliation and Disclaimer:** We are not affiliated, associated, authorized, endorsed by, or in any way officially connected with the GitHub,  NCN, or Zenodo.



# How to

1. Add a `LICENSE` file to your GitHub repository [as we did here](LICENSE), if you don't have one. You can read more about adding a license to the GitHub repository [here](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/adding-a-license-to-a-repository).

2. In your repository, create a `CITATION.cff` file with a citation details.
    - Use [this wizard](https://citation-file-format.github.io/cff-initializer-javascript) to create a CITATION.cff file, basing on [ours](CITATION.cff) as an example (alternatively, you can customize our CITATION.cff file, but it is more convenient to use the wizard). <br />
:warning: Add the DOI identifier field and temporarily put there any DOI, you will later change it to the DOI obtained via Zenodo for your repository.
    - The format of the file is YAML
    - License: our grant agency, NCN, requires the datasets to be published under the CC0 1.0 licence. What about software? :question:
    - After commit, the citation tool will be available on the right repository panel:<br />
![](obrazki/image-2023-01-02-11-42-28.png)

3. In your repository, create a `.zenodo.json` file. You can edit the [this sample one here](.zenodo.json).
   - Add your grant number in the field *"notes"* 
   <br />:warning: Polish grants **do not** work with the dedicated field "grants/funding"
   - More information on the format and fields are [available here](https://developers.zenodo.org/#introduction)
   - The format of the file is json
   - license: our grant agency requries the datasets to be licensed under CC0 1.0 or CC BY 4.0 (NCN’s Open Access Policy was recently relaxed in certain cases, see details at [NCN website](https://www.ncn.gov.pl/en/aktualnosci/2023-11-17-zlagodzenie-polityki-oa-materialy-z-webinarium).

<br />

📢
**At this point, you should make your repository [publicly available](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility).**

<br />

4. Connect Zenodo to GitHub (or vice versa) as [described here](https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content).
   - Your GitHub settings will be available at [https://zenodo.org/account/settings/github/](https://zenodo.org/account/settings/github/).
   - Enable the integration by switching the repository on:<br />
![](obrazki/image-2023-01-02-11-50-58.png)
   - Go to GitHub and make your first [release](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository) (or pre-release):<br />
![](obrazki/image-2023-01-02-11-52-51.png)<br />
![](obrazki/image-2023-01-02-11-54-11.png)
   - At this point your repository will be visible at the appropriate Zenodo page. Please note the status - green means ok, orange means processing, red means error<br />
![](obrazki/image-2023-01-02-11-55-57.png)
   - At this point you can add a repository DOI identifier issued by Zenodo to the `CITATION.cff` file (see above). See below on how to get the universal DOI

5. New DOI is generated every time you do a release (or pre-release) of your repository. To get the one-universal DOI for your repository, at the Zenodo page:
   - Move to the the GitHub panel
   - Select your repository from the Enabled Repositories panel
   - Click DOI for any of the releases, you will be redirected to the Zenodo page of your published repository
   - In the right panel, look for *Cite all versions? You can cite all versions by using the DOI...*:<br />
![](obrazki/image-2023-01-02-12-07-39.png)
> **_NOTE:_**  You can also add a cool zenodo badge to your repository:
  [![DOI](https://zenodo.org/badge/584345819.svg)](https://zenodo.org/badge/latestdoi/584345819)

## Additional remarks and optional steps:

1. You may want to enable GitHub actions to check validity of `CITATION.cff`, as is done in this repository (`.github/workflows/cffconvert.yml`). You will get a cool badge: [![cffconvert](https://github.com/filipsPL/NCN-github-OA/actions/workflows/cffconvert.yml/badge.svg)](https://github.com/filipsPL/NCN-github-OA/actions/workflows/cffconvert.yml)
1. When the paper is published and has DOI assigned, you may add this info to `CITATION.cff` file in `identifiers` section.

# Unanswered questions

1. The GitHub repository has an unique DOI, and the following up, peer-reviewed scientific paper also has its own DOI. We (the scientists) want to get citations from the scientific paper. Questions:
   - shall we require others to cite both GitHub repo and scientific paper? Or only the paper?
   - if both are cited, can we merge both citations (eg in Google Scholar)?

# Discussion

Feel free to discuss these matters on the [Discussions](https://github.com/filipsPL/NCN-github-OA/discussions) page.
