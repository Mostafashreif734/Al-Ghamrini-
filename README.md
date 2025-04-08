import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { Input } from "@/components/ui/input"; import { useState } from "react"; import { Search } from "lucide-react"; import { Tabs, TabsList, TabsTrigger } from "@/components/ui/tabs";

export default function ElGhamreinyStore() { const [search, setSearch] = useState(""); const [category, setCategory] = useState("all");

return ( <div className="min-h-screen bg-[#f9f9f9] text-gray-900 p-4"> <header className="text-center py-6"> <h1 className="text-4xl font-bold mb-2">الغامريني ستور</h1> <p className="text-lg">إلكترونيات - إكسسوارات - ديكورات منزلية</p> </header>

<div className="flex flex-col items-center gap-4 my-4">
    <div className="flex gap-2 w-full max-w-md">
      <Input
        placeholder="ابحث عن منتج..."
        value={search}
        onChange={(e) => setSearch(e.target.value)}
      />
      <Button><Search className="h-4 w-4" /></Button>
    </div>

    <Tabs defaultValue="all" className="w-full max-w-md">
      <TabsList className="w-full justify-between">
        <TabsTrigger value="all" onClick={() => setCategory("all")}>الكل</TabsTrigger>
        <TabsTrigger value="accessories" onClick={() => setCategory("accessories")}>إكسسوارات</TabsTrigger>
        <TabsTrigger value="electronics" onClick={() => setCategory("electronics")}>إلكترونيات</TabsTrigger>
        <TabsTrigger value="home" onClick={() => setCategory("home")}>ديكور منزلي</TabsTrigger>
      </TabsList>
    </Tabs>
  </div>

  <section className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
    {[1, 2, 3, 4, 5, 6].map((item) => (
      <Card key={item} className="rounded-2xl shadow-md">
        <CardContent className="p-4">
          <img src="https://via.placeholder.com/300x200" alt="منتج" className="rounded-xl mb-4" />
          <h2 className="text-xl font-semibold mb-2">اسم المنتج</h2>
          <p className="text-sm text-gray-600 mb-2">وصف مختصر عن المنتج المعروض</p>
          <p className="text-lg font-bold mb-2">EGP 499.00</p>
          <div className="flex flex-col gap-2">
            <Button className="w-full">أضف إلى السلة</Button>
            <Button variant="outline" className="w-full text-xs">الدفع عبر فودافون كاش</Button>
            <Button variant="outline" className="w-full text-xs">الدفع عبر Visa/PayPal</Button>
          </div>
        </CardContent>
      </Card>
    ))}
  </section>

  <footer className="text-center mt-12 text-sm text-gray-500">
    © 2025 الغامريني ستور - mostafasherif66<br/>
    <a href="https://instagram.com/mostafasherif66" target="_blank" className="underline">تابعنا على السوشيال ميديا</a>
  </footer>
</div>

); }

