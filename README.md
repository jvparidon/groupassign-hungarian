# groupassign-hungarian
Assign people to groups based on rank preference using the Hungarian algorithm.

The Hungarian algorithm is a deterministic[1] procedure to find a (close to) optimal assignment of participants to groups. The script can handle any number of groups and participants, as long as the number of participants does not exceed the number of groups times the maximum group size.

## How to use groupassign-hungarian
Set the maximum group size using `--max_group_size` and specify a comma-separated text file of preferences using `--filename` (an `example_preferences.txt` file is provided).

Optional: The script will weight missing preferences according to a pre-specified penalty (`--na_weight`, default is 99) so if you have 10 groups, but only a top 3 of preferences for each participant the script will handle the missing values. Additionally, you can change the discount function that is applied to the rank preferences using `--discount`.

## Examples
Run `python3 groupassign-hungarian.py --help` for command line options.

Run `python3 groupassign-hungarian.py --filename=example_preferences.txt --max_group_size=3` for an example of group assignments using the included `example_preferences.txt` file.

If you have a small number of groups (less than 20) you will be fine using the default settings for `--na_weight` and `--discount`.

---
[1] Even though the algorithm is deterministic, this script uses randomization to guarantee fairness and will therefore not yield the same outcome every time if there are multiple optimal solutions.
