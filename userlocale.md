---
theme: geolytix
_class: lead
paginate: true
__backgroundColor: #fff
__backgroundImage: url(./assets/backgrounds/title-photo-pink.jpeg)
---

<style scoped>
section * {
  text-align: right;
}
h1 {
  border-bottom: none !important;
  color: var(--color-primary) !important;
}
</style>

![bg grayscale:1](./assets/backgrounds/overlay-pink.png)

<!-- _class: lead -->

# Mapp Next

## What are we trying to archive?

 Less deployments :rocket:
 More tests :microscope:
 Less bugs :bug:
 Save Time :watch:

---

<style scoped>
section code {
  font-size: 40px;
}
</style>

# What is our current Structure?

```bash
workspace
├── templates
└── locale(s)
    └── layers
        └── roles
```

> **Note:** Most objects and arrays can have roles

---

<!-- _class: lead -->

# What do we want?


<style scoped>
section * {
  font-size: 40px;
}
</style>

- Data/Product driven
- Accessible
- Turn Key
- Robust

---

# How can we get there?

- Shared templates (data driven)
- Role levels (accessible)
- Dynamic/User Locales (Turn Key)
- Mono repo (Robust)

---

# Mono repo (Robust)

- Single source of truth
- ++ Dev ex
- Better testing
- Automation

---

# Dynamic Locales (UserLocales)

> developed by Dennis to save away a locale objects for a user.

| Pros ✅ | Cons ❌|
|------|------|
| Locales for different users/clients | Potential for divergent configurations |
| On the fly creation | Requires developer/user discipline to maintain |
| Can be used to package data products |  |
| Turn key solution | |
| Less Deployments | |

---

# Shared Templates (Sub Module)

- Already in place
- Configurations are all driven by product/data
- It is a catalog

---

# Roles

- Already in place
- nested (n) (Tree 🎄)
  - locale --> template --> object

> $$
> n^n
> $$

---

# How can this all fit? (Mapp Next)

- Providing a catalog of data to the user
  - via a plugin or some core functionality.
- Create a Dynamic Locale from this catalog of data
- Assign said locale to users based on their role
  - (And even allow them to be extended)
- Changes on shared Templates/Product reflect easily

---

# Admin Journey?

![]('./assets/di')
