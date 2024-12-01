<script>
      import { Button } from "$lib/components/ui/button/index";
      import { Bell, CheckCircle2, Images, MessageSquareText, Plus, Shuffle, Smile, Tag } from "lucide-svelte";

      // Add message data
      const messages = [
          {
              initials: "RD",
              name: "Rory Dredhart",
              message: "Hello guys",
              time: "10:20PM",
              color: "bg-primary"
          },
          {
              initials: "CG",
              name: "Cris George",
              message: "Hello guys",
              time: "10:20PM",
              color: "bg-primary"
          },
          {
              initials: "JP",
              name: "Jake Paul",
              message: "Hi nice to meet you",
              time: "08:45PM",
              color: "bg-primary"
          }
      ];
</script>

<div class="h-[90vh] flex flex-col gap-3 p-4 bg-gray-100">
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

    <div class="flex-1 flex gap-5 min-h-0">
        <div class="w-1/2 bg-white rounded-xl flex flex-col">
            <div class="flex-1 overflow-y-auto">
                <div class="flex flex-col divide-y px-5">
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
        </div>

        <div class="w-1/2 bg-white rounded-xl flex flex-col">
            <div class="flex-1 flex items-center justify-center ">
                <div class="text-center">
                    <div class="mb-2">
                       <MessageSquareText class="w-16 h-16 mx-auto opacity-50" />
                    </div>
                    <p>No conversation selected.</p>
                </div>
            </div>

            <div class="border-t p-4">
                <div class="flex gap-4 mb-4">
                    <button class="text-primary border-b-2 border-primary pb-2">Message</button>
                    <button class=" pb-2">Note</button>
                </div>
                <div class="w-full">
                    <input type="text" placeholder="Type a message..." class="flex-1 bg-transparent py-3 focus:outline-none w-full">
                </div>
                <div class="flex gap-2 ">
                    <div class="flex items-center gap-2 rounded-lg  w-full justify-between">
                        <div class="flex items-center gap-6">
                          
                                <Smile class="h-5 w-5 " />
                           
                          
                                <Images class="h-5 w-5 " />
                           
                        </div>
                        <Button class="bg-primary hover:bg-blue-700 text-white px-6 text-sm font-semibold">
                            SEND
                        </Button>
                    </div>
                  
                </div>
            </div>
        </div>
    </div>
</div>
