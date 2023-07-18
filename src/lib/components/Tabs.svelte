<script>
  import { onMount } from 'svelte';

  let withdraw = 0;
  let deposit = 0;
  onMount(() => {
    const tabButtons = document.querySelectorAll('[role=tab]');
    tabButtons.forEach((tabButton) => {
      tabButton.addEventListener('click', (e) => {
        e.preventDefault();
        const tabContainer = e.target.parentElement.parentElement;
        const targetId = e.target.getAttribute('aria-controls');
        tabButtons.forEach((_tabButton) => _tabButton.setAttribute('aria-selected', false));
        tabButton.setAttribute('aria-selected', true);
        tabContainer
          .querySelectorAll('[role=tabpanel]')
          .forEach((tabPanel) => tabPanel.setAttribute('hidden', true));
        tabContainer.querySelector(`[role=tabpanel]#${targetId}`).removeAttribute('hidden');
      });
    });
  });
</script>

<section class="tabs">
  <menu role="tablist" aria-label="Tabs Template">
    <button role="tab" aria-controls="tab-A" aria-selected="true">Tab A</button>
    <button role="tab" aria-controls="tab-B">Tab B</button>
    <button role="tab" aria-controls="tab-C">Tab C</button>
  </menu>
  <article role="tabpanel" id="tab-A">
    <figure>
      <blockquote>
        "Ignorance is not bliss. Ignorance is poverty. Ignorance is devastation. Ignorance is
        tragedy. And ignorance is illness. It all stems from ignorance."
        <footer>
          <cite>– Jim Rohn</cite>
        </footer>
      </blockquote>
    </figure>
  </article>
  <article role="tabpanel" id="tab-B" hidden>
    <figure>
      <blockquote>
        "Nothing beats a simple worldview. When we know who is the bad guy, the day has structure."
        <footer>
          <cite>– Volker Pispers</cite>
        </footer>
      </blockquote>
    </figure>
  </article>
  <article role="tabpanel" id="tab-C" hidden>
    <figure>
      <blockquote>
        "When you're new to something, you bring an ignorance that can be highly innovative."
        <footer>
          <cite>– Rick Rubin</cite>
        </footer>
      </blockquote>
    </figure>
  </article>
</section>

<style>
  /* [role='tabs'] {
    display: flex;
  }

  [role='tabs'] section {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
  }

  [role='tabs'] figure {
    flex-grow: 1;
    width: 100%;
    height: 100%;
    display: none;
  } */

  [role='tablist'] {
    margin: 4px 0px 0px 0px;
    display: flex;
    flex-direction: row;
  }

  button[role='tab'] {
    width: 100px;
    margin: 0px 1px 0px 1px;
    padding: 8px;
    border-radius: 10px 10px 0% 0%;
  }

  article[role='tabpanel'] {
    margin: 0px 4px 6px 4px;
    padding: 4px;
    border-radius: 0% 0%;
  }

  figure {
    margin: 0px;
    padding: 0px;
  }

  blockquote {
    margin: 0px;
    padding: 4px;
  }

  /* [role='tabs'] [type='radio']:checked + figure {
    display: block;
  }

  nav[role='tab-control'] label.active {
    color: var(--primary);
    cursor: pointer;
  } */
</style>
