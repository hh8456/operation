<https://github.com/jaksal/dbdiff>

eg.

* 把 im_develop 同步到 im_first_phase_online, 即把 im_first_phase_online 变得和 im_develop 一样

dbdiff -diff_type=schema -source="dev:dev123@tcp(xxx.xxx.xxx.xxx:3306)/im_develop" -target="dev:dev123@tcp(xxx.xxx.xxx.xxx:3306)/im_first_phase_online" -output=output.sql