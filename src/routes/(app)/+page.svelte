<script>
      import { Button } from "$lib/components/ui/button/index";
      import { Bell, CheckCircle2, Plus, Shuffle, Tag } from "lucide-svelte";

      // Add message data
      const messages = [
          {
              initials: "RD",
              name: "Rory Dredhart",
              message: "Hello guys",
              time: "10:20PM",
              color: "bg-blue-600"
          },
          {
              initials: "CG",
              name: "Cris George",
              message: "Hello guys",
              time: "10:20PM",
              color: "bg-blue-600"
          },
          {
              initials: "JP",
              name: "Jake Paul",
              message: "Hi nice to meet you",
              time: "08:45PM",
              color: "bg-blue-600"
          }
      ];
</script>
<div class="max-h-screen flex flex-col gap-3">

<div class="h1 font-semibold text-2xl">Inbox</div>
<div class="w-full h-[61px] bg-white rounded-lg px-8 flex items-center justify-between">
    <h3 class="text-xl font-normal leading-8">
All
    </h3>
    <div class="actions flex items-center gap-2">
        <Button variant="ghost" class="hover:bg-transparent">
            <Tag class="text-3xl" size="33" />
        </Button>
        <Button variant="ghost" class="hover:bg-transparent">
            <Shuffle class="text-3xl" size="33" />
        </Button>
        <Button variant="ghost" class="hover:bg-transparent">
            <Bell class="text-3xl" size="33" />
        </Button>
        <Button variant="ghost" class="hover:bg-transparent">
            <CheckCircle2 class="text-3xl" size="33" />
        </Button>
    </div>
</div>

<div class="flex items-center gap-5">
    <div class="w-1/2 bg-white rounded-xl h-full p-4">
        <div class="flex flex-col divide-y">
            {#each messages as msg}
                <div class="flex items-center gap-4 py-4">
                    <div class="flex-shrink-0">
                        <div class="w-14 h-14 rounded-full {msg.color} text-white flex items-center justify-center text-xl">
                            {msg.initials}
                        </div>
                    </div>
                    <div class="flex-grow">
                        <div class="flex items-center justify-between">
                            <h4 class="text-lg font-medium">{msg.name}</h4>
                            <span class="font-medium">{msg.time}</span>
                        </div>
                        <p class="font-light">{msg.message}</p>
                    </div>
                </div>
            {/each}
        </div>
    </div>
    <div class="w-1/2 bg-white rounded-xl h-full">
    </div>
</div>
</div>
