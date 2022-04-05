<script>
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    const clickBackgroundEvent = async(event) => {
        console.log(event.target.classList)
        if (event.target.classList.contains("widget-popup-wrapper")) {
        dispatch("closePopup", {
            text: "close",
            });
        }
    }

    let button_text="Enroll"

    function handleClick() {
        button_text = "Enrolled!"

        var button_ob = document.getElementById('cart-button')
        button_ob.classList.add('btn-added-to-cart')
    }
</script>

<div class="widget-popup-wrapper" on:mousedown={clickBackgroundEvent}>
    <div class="widget-popup">
        <span style="display: flex">
            <svg
            class="cart-exit"
            on:click={() =>
                dispatch("closePopup", {
                text: "close",
                })}
            xmlns="http://www.w3.org/2000/svg"
            height="24px"
            viewBox="0 0 24 24"
            width="24px"
            fill="#000000"
            ><path d="M0 0h24v24H0V0z" fill="none" /><path
                d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12 19 6.41z"
            /></svg>
            <div class="text-uppercase fw-bold text-xs mb-1" style="margin-left: 5%; font-size: 22px; color: rgb(157, 25, 57);">Cart</div>
        </span>

        <span style="display: flex; height: 100%;">
            <div class="timetable-wrapper" style="width: 50%;">
                <div class="fw-bold text-xs mb-1 center" style="font-size: 17px; color: rgb(157, 25, 57); width: fit-content;">Timetable</div>
                <img class="timetable center" src="https://i.imgur.com/DBGdJg2.jpeg" alt="timetable">
            </div>
            <div class="courses" style="width: 50%;">
                <div class="fw-bold text-xs mb-1 center" style="font-size: 17px; color: rgb(157, 25, 57); width: fit-content;">Courses</div>
                <ul>
                    {#each window.cartData as course}
                        <li>
                            <span style="display: flex">
                                <div class="product-widget">
                                    <div style="font-size: 14px;">
                                        {course.id}: {course.description}
                                    </div>
                                    
                                </div>
                            </span>
                        </li>
                    {/each}
                </ul>
                <div
                id='cart-button'
                class="btn btn-primary btn-enroll"
                type="button"
                on:click={handleClick}>{button_text}</div
              >
            </div>
        </span>
            
            
            
    </div>
    
</div>

<style>
  .btn-enroll {
    position: absolute;
    bottom: 0;
    right: 0;
    margin-bottom: 10px;
    margin-right: 10px;
    font-size: 20px;
  }

  .cart-exit:hover {
    background: #f0f0f0;
    cursor: pointer;
  }

  .widget-popup-wrapper {
    z-index: 25;
    position: fixed;
    background-color: rgba(0, 0, 0, 0.36);
    right: 0;
    top: 0;
    bottom: 0;
    left: 0;
  }

  .widget-popup {
    position: fixed;
    background-color: #fff;
    margin: 0 auto;
    padding: 15px;
    top: 10%;
    right: 10%;
    left: 10%;
    height: 80%;
    border-radius: 5px;
    box-shadow: 0 19px 38px rgba(0, 0, 0, 0.12), 0 15px 12px rgba(0, 0, 0, 0.14);
    -webkit-animation: slide 0.2s forwards;
    animation: slide 0.2s forwards;
    opacity: 1;
    transition: opacity 0.2s;
    overflow: hidden;
    display: flex;
    flex-direction: column;
  }
  
    .product-widget {
        border-radius: 5px;
        box-shadow: 0 5px 20px rgb(0 0 0 / 7%), 0 10px 12px rgb(0 0 0 / 6%);
        text-align: center;
        padding: 1em 0 0 0;
        margin: 0 auto;
        padding-bottom: 2%;
        width: 95%;
    }

    .timetable {
        width: 90%;
    }

    .center {
        display: block;
        margin-left: auto;
        margin-right: auto;
    }

    :global(.btn-added-to-cart) {
    background-color: #f5f5f5 !important;
    color: #000 !important;
    cursor: default !important;
  }
</style>
