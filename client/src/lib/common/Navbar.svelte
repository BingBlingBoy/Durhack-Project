<script lang="ts">
  import Searchbar from "./Searchbar.svelte";
  import logo from "$lib/images/whaleLogo.png";
  import { authStore } from "$lib/stores";
  import type { User } from "firebase/auth";

  let user: User;

  authStore.subscribe((u) => (user = u));
</script>

<div class="flex items-center bg-primary text-white pt-4 px-4 justify-between">
  <li>
    <a href="/">
      <img class="w-16 h-16" src={logo} alt="logo" />
    </a>
  </li>

  <Searchbar />

  <ul class="flex items-center justify-between gap-4">
    <li>
      <a href="/basket">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-6 h-6"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 00-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 00-16.536-1.84M7.5 14.25L5.106 5.272M6 20.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm12.75 0a.75.75 0 11-1.5 0 .75.75 0 011.5 0z"
          />
        </svg>
      </a>
    </li>
    <li>
      <a href={user ? "/user/dashboard" : "/user/login"}>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-6 h-6"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M15.75 6a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0zM4.501 20.118a7.5 7.5 0 0114.998 0A17.933 17.933 0 0112 21.75c-2.676 0-5.216-.584-7.499-1.632z"
          />
        </svg>
      </a>
    </li>
  </ul>
</div>
