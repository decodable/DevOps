```
blockdiag docker {
    default_shape = roundedbox;
    default_group_color = "#FFFFFF";
    span_width = 120;  // default value is 64

    A [label = "Dockerfile"];
    B [label = "Docker Image"];
    C [label = "Docker Container"];
    D [label = "Git Repository"];
    E [label = "Local Disk"];
    F [label = "Docker Repository"];

    group {
        A; B; C;
        orientation = portrait;
    }
    group {
        D; F;
    }

    D <-> A [label = "push/pull"];
    F <-> B [label = "push/pull"];
    A -> B;
    B <-> C;
    B <-> E [label = "load/save"];
}
```

[Permanent link for this diagram](http://interactive.blockdiag.com/?compression=deflate&src=eJx9kMFOhDAURffzFS_j2qDGuKmaDCDGxJVbY8iDdqCZymvaMmrM_LulTEcIxq4o5_T29VaK6h2X2AD3H8LA9wr84mKLvXKlbVELuANDfccFr-iTzXjjgS5rUmS8tT4rwlqPktXYlR-Su9azy6sLBpAk8SjsUfUCpIWb61XQN_CqsBJqCMrDMFupxPptDEsXFJ7esTnxbMkz6hzKTpjo5BPnUTp4EZqsdGS-ovEwMZ6pRgW5tLtIi-Ud84hghU6OPYZ3MUgZZOz0g4wUfjInqfNJmowzKN3ID39G5AyKyI8vuT2_nzWme9smulfqd9hBSf9TNjAYsd9Bz6abaRmKkCcW96Hvww9Mm5zY)
