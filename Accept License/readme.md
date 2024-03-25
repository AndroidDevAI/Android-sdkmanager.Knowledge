# Automatically Accept Android Licenses
sch:
- https://www.google.com/search?q=sdkmanager+--licenses+accept+all

Discuss:
- https://stackoverflow.com/questions/38096225/automatically-accept-all-sdk-licences/75933762#75933762

## works:
- https://github.com/mataha/android-accept-licenses
    - ark: https://web.archive.org/web/20240325064028/https://github.com/mataha/android-accept-licenses

shell:
```
bash -c "yes 'y' | sdkmanager --licenses"
```

ansible:
```
- name: Accept all Licenses
  ansible.builtin.shell: |
    bash -c "yes 'y' | sdkmanager --licenses"
  args:
    creates: "{{ android_home }}/licenses"
```
