## Modifications

Go to vendor\laravel\jetstream\src\Http\Livewire\UpdateProfileInformationForm.php

Modify this:

``   public function mount()
    {
        $user = Auth::user();

        $this->state = array_merge([
            'email' => $user->email,
        ], $user->withoutRelations()->toArray());
        $this->state['experience'] = Doctor::where('doctor_id', Auth::user()->id)->first()->experience;
        $this->state['bio_data'] = Doctor::where('doctor_id', Auth::user()->id)->first()->bio_data;
        $this->state['category'] = Doctor::where('doctor_id', Auth::user()->id)->first()->category;
    }
``