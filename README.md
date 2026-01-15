Custom rosdep rules.

# 1) Make sure rosdep is initialized at least once on the machine
# (skip if you've already done this before)
sudo rosdep init  # may say "already exists"; that's fine
rosdep update

# 2) Add the DTI rules to rosdep sources
echo "yaml https://raw.githubusercontent.com/teknologisk-institut/dti_rosdep_rules/main/custom.yaml" \
  | sudo tee /etc/ros/rosdep/sources.list.d/42-dti.list >/dev/null

# 3) Refresh rosdep’s cache
rosdep update

Convenience links and background knowledge:

https://docs.ros.org/en/kilted/Tutorials/Intermediate/Rosdep.html

https://docs.ros.org/en/independent/api/rosdep/html/

https://github.com/ros/rosdistro/blob/master/CONTRIBUTING.md#rosdep-rules-contributions

