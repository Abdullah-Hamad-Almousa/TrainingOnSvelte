<script lang="ts">

    let s = $state("Abdullah")

    function changeName() {
        if (s === "Abdullah") {
            s = "Hamad"
        } else if (s === "Hamad") {
            s = "Abdullah"
        }
    }

</script>

<p>
    My name is {s.toUpperCase()}
</p>

<button onclick={changeName}>
    change name
</button>