<https://github.com/jaksal/dbdiff>

eg.

* �� im_develop ͬ���� im_first_phase_online, ���� im_first_phase_online ��ú� im_develop һ��

dbdiff -diff_type=schema -source="dev:dev123@tcp(xxx.xxx.xxx.xxx:3306)/im_develop" -target="dev:dev123@tcp(xxx.xxx.xxx.xxx:3306)/im_first_phase_online" -output=output.sql