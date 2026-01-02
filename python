import flet as ft

def main(page: ft.Page):
    page.title = "Aplikasi OSIS"
    page.theme_mode = ft.ThemeMode.LIGHT
    page.window_width = 400  # Ukuran simulasi HP
    page.window_height = 700

    # Konten untuk setiap halaman
    def get_content(index):
        if index == 0:
            return ft.Column([
                ft.Text("Beranda OSIS", size=30, weight="bold"),
                ft.Text("Selamat datang di aplikasi resmi OSIS sekolah!")
            ])
        elif index == 1:
            return ft.Text("Halaman Kalender Kegiatan", size=25)
        elif index == 2:
            return ft.Text("Ruang Chat Siswa", size=25)
        elif index == 3:
            # Logika Level Game Ular Tangga (365 Level)
            return ft.Column([
                ft.Text("Game Ular Tangga OSIS", size=25),
                ft.Text("Progress: Level 1 / 365 Hari", italic=True),
                ft.ProgressBar(value=1/365, color="green")
            ], scroll=ft.ScrollMode.AUTO)

    # Fungsi untuk merubah tampilan saat ikon diklik
    def on_nav_change(e):
        index = e.control.selected_index
        page.clean()
        page.add(get_content(index), nav_bar)
        page.update()

    # Membuat Bottom Navigation Bar
    nav_bar = ft.NavigationBar(
        destinations=[
            ft.NavigationDestination(icon=ft.icons.HOME, label="Beranda"),
            ft.NavigationDestination(icon=ft.icons.CALENDAR_MONTH, label="Kalender"),
            ft.NavigationDestination(icon=ft.icons.CHAT_BUBBLE, label="Pesan"),
            ft.NavigationDestination(icon=ft.icons.CASINO, label="Game"), # Ikon dadu untuk game
        ],
        on_change=on_nav_change,
        selected_index=0
    )

    # Tampilan awal (Beranda)
    page.add(get_content(0), nav_bar)

ft.app(target=main)
